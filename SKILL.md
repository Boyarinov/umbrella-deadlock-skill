---
name: deadlock-lua
description: Write Lua scripts for the Umbrella cheat framework in Valve's Deadlock (Source 2 / Citadel). Covers callbacks, entities, rendering, menu, tracing, input, and render target optimization.
globs:
  - "**/*.lua"
---

# Deadlock Lua Scripting (Umbrella Framework)

You write Lua 5.4 scripts for the Umbrella framework targeting Valve's Deadlock.
This is NOT Dota 2 scripting. The API is completely different.

## How to use this skill

This skill contains compact API patterns below and full reference docs as companion files.
**Do NOT guess API signatures.** Before using any function, `read` the relevant doc file.

### API reference lookup table

Read the file listed in the right column to find exact function signatures, parameter types, and return types.

| Topic | Read this file |
|-------|---------------|
| Entity methods (get_origin, get_velocity, get_health, get_bones, etc.) | `skill://deadlock-lua/docs/entities.md` |
| Player pawn methods (simulate_movement, get_tech_resist, etc.) | `skill://deadlock-lua/docs/entities.md` |
| Ability methods (get_scaled_property, find_entities_in_cone, etc.) | `skill://deadlock-lua/docs/entities.md` |
| Modifier methods | `skill://deadlock-lua/docs/entities.md` |
| Entity list (local_pawn, by_class_name, by_index, etc.) | `skill://deadlock-lua/docs/entities.md` |
| Render API (Text, FilledRect, Circle, WorldToScreen, LoadFont, etc.) | `skill://deadlock-lua/docs/rendering.md` |
| Render targets (FindOrCreateRT, RenderToRT, DrawRT) | `skill://deadlock-lua/docs/rendering.md` |
| Vertex class | `skill://deadlock-lua/docs/rendering.md` |
| CUserCmd fields and methods (smooth_aim, buttonstate, psilent, etc.) | `skill://deadlock-lua/docs/input-commands.md` |
| Input (is_pressed, is_key_down, get_cursor_pos, etc.) | `skill://deadlock-lua/docs/input-commands.md` |
| Convar access | `skill://deadlock-lua/docs/input-commands.md` |
| All callback signatures (on_createmove, on_frame, on_key_event, etc.) | `skill://deadlock-lua/docs/callbacks.md` |
| Trace functions (line, hull, bullet, bullet_hitbox) | `skill://deadlock-lua/docs/tracing.md` |
| Utils (calc_angle, get_fov, predict_bullet, find_target_in_fov, etc.) | `skill://deadlock-lua/docs/utilities.md` |
| Database persistence (db) | `skill://deadlock-lua/docs/utilities.md` |
| Global context (shared cross-script state) | `skill://deadlock-lua/docs/utilities.md` |
| Meta tracker (rank, period) | `skill://deadlock-lua/docs/utilities.md` |
| Game rules (game_time, is_pre_game, etc.) | `skill://deadlock-lua/docs/utilities.md` |
| Global vars (tick_interval, tick_count, etc.) | `skill://deadlock-lua/docs/utilities.md` |
| Net channel | `skill://deadlock-lua/docs/utilities.md` |
| Menu navigation (Create, Find, tabs, groups) | `skill://deadlock-lua/docs/menu.md` |
| CMenuSwitch (toggle widget) | `skill://deadlock-lua/docs/menu/switch.md` |
| CMenuBind (key bind widget) | `skill://deadlock-lua/docs/menu/bind.md` |
| CMenuButton | `skill://deadlock-lua/docs/menu/button.md` |
| CMenuSliderFloat / CMenuSliderInt | `skill://deadlock-lua/docs/menu/slider-float.md` or `skill://deadlock-lua/docs/menu/slider-int.md` |
| CMenuColorPicker | `skill://deadlock-lua/docs/menu/color-picker.md` |
| CMenuComboBox / CMenuMultiComboBox | `skill://deadlock-lua/docs/menu/combo-box.md` or `skill://deadlock-lua/docs/menu/multi-combo-box.md` |
| CMenuMultiSelect | `skill://deadlock-lua/docs/menu/multi-select.md` |
| CMenuInputBox | `skill://deadlock-lua/docs/menu/input-box.md` |
| CMenuLabel | `skill://deadlock-lua/docs/menu/label.md` |
| CMenuGearAttachment / CMenuColorPickerAttachment | `skill://deadlock-lua/docs/menu/gear-attachment.md` or `skill://deadlock-lua/docs/menu/color-picker-attachment.md` |
| Panorama UI interaction | `skill://deadlock-lua/docs/panorama.md` |
| HTTP requests | `skill://deadlock-lua/docs/http.md` |
| Color, Vector, Angle, Vec2 constructors and methods | `skill://deadlock-lua/docs/types.md` |
| Target selection system | `skill://deadlock-lua/docs/target-selection.md` |
| Notifications | `skill://deadlock-lua/docs/notifications.md` |
| Raw struct field access | `skill://deadlock-lua/docs/raw-struct.md` |
| All enums (ButtonCode, InputBitMask_t, FontCreate, EModifierState, etc.) | `skill://deadlock-lua/docs/enums.md` |

For a complete onboarding walkthrough: `skill://deadlock-lua/docs/getting-started.md`

## Script structure

Scripts are `.lua` files placed in the `scripts/` folder. No `require()`. No return-table export.

### Load order
Files load alphabetically. Use numeric prefixes for libraries:
```
1_utility.lua    -- loaded first, exposes globals
2_hero_lib.lua   -- uses utility
haze.lua         -- hero script, uses both
```

### Shared state
Scripts share code through globals (no module system):
```lua
-- In 1_lib.lua
MY_LIB = {}
function MY_LIB.helper() end

-- In script.lua (loaded later)
MY_LIB.helper()
```

### Minimal script
```lua
callback.on_frame:set(function()
    -- runs every rendered frame
end)
```

### Standard skeleton
```lua
-- Menu (runs once at load)
local tab = Menu.Create("General", "Section", "Tab", "SubTab")
local group = tab:Create("Settings")
local enabled = group:Switch("Enable", false)
local speed = group:Slider("Speed", 0.0, 100.0, 50.0)

-- Resources (load once)
local font = Render.LoadFont("Arial", Enum.FontCreate.FONTFLAG_ANTIALIAS)

-- Logic callback (tick-rate)
callback.on_createmove:set(function(cmd)
    if not enabled:Get() then return end
    -- movement/aim logic here
end)

-- Render callback (frame-rate)
callback.on_frame:set(function()
    if not enabled:Get() then return end
    Render.Text(font, 16, "Active", Vec2(100, 100), Color(0, 255, 0))
end)
```

## Critical patterns

### Callback registration
```lua
callback.on_xxx:set(fn)    -- subscribe
callback.on_xxx:unset(fn)  -- unsubscribe (same reference)
```
Anonymous functions cannot be unregistered. Key callbacks:
- `on_createmove(cmd)` -- tick-rate logic, aim, movement
- `on_frame()` -- rendering (every frame)
- `on_draw()` -- rendering (after on_frame)
- `on_key_event(data) -> boolean` -- input; return false to block
- `on_add_entity(ent)` / `on_remove_entity(ent)` -- entity lifecycle
- `on_add_modifier(mod, target, owner)` / `on_remove_modifier(mod, target)`
- `on_bullet_create(data)` -- bullet events
- `on_particle_create/update/destroy(data)` -- particle events

### Entity access
```lua
local pawn = entity_list.local_pawn()          -- player_pawn|nil
local ctrl = entity_list.local_controller()    -- entity|nil
local pawns = entity_list.by_class_name("C_CitadelPlayerPawn")  -- entity[]

-- ALWAYS validate before use
if not pawn or not pawn:valid() then return end
local pos = pawn:get_origin()  -- Vector|nil (nil-check required)
if not pos then return end
```

Entity types are polymorphic: `entity`, `player_pawn`, `ability`.
Class names: `C_CitadelPlayerPawn`, `C_CitadelBaseAbility`, etc.

### Abilities and properties
```lua
local ability = pawn:get_ability("ability_sleep_dagger")
if ability then
    local cast_delay = ability:get_scaled_property("AbilityCastDelay")
    local in_cast = ability.m_bInCastDelay  -- raw struct field access
end
```

### Movement / CUserCmd
```lua
callback.on_createmove:set(function(cmd)
    cmd.forwardmove = 450
    cmd.leftmove = 0
    cmd:add_buttonstate1(InputBitMask_t.IN_JUMP)
    cmd:add_buttonstate2(InputBitMask_t.IN_JUMP)
    -- Use add/clear methods, NOT direct field writes (protobuf sync)

    -- Aim:
    local angle = utils.calc_angle(cmd.orig_vec_camera_position, target_pos)
    cmd:smooth_aim(angle, 15.0)
end)
```

### Tracing
```lua
local result = trace.line(start, finish,
    0x1C1003,  -- content mask (CONTENTS flags)
    0,         -- exclude mask
    0,         -- solid type
    7,         -- object set mask (overridden internally to 0xF)
    4,         -- collision group
    function(ent) return true end  -- true = INCLUDE (not ignore!)
)
if result.fraction < 1.0 then
    -- hit at result.entity
end
```

### Render target optimization
Use for static/rarely-changing HUD elements. Do NOT use for content that changes every frame.
```lua
local rt = Render.FindOrCreateRT("my_rt", 400, 200)  -- allocate once
local dirty = true

callback.on_frame:set(function()
    if dirty then
        dirty = false
        Render.RenderToRT(rt, function()
            -- draw at Vec2(0,0) -- RT-local coordinates
            Render.FilledRect(Vec2(0, 0), Vec2(400, 200), Color(20, 20, 20, 200))
            Render.Text(font, 16, "Cached", Vec2(10, 10), Color(255, 255, 255))
        end)
    end
    Render.DrawRT(rt, Vec2(50, 50), Color(255, 255, 255))  -- blit (cheap)
end)
-- Set dirty = true when content changes
```

### WorldToScreen
```lua
local screen, visible = Render.WorldToScreen(world_pos)
if visible then
    Render.Text(font, 14, "Target", screen, Color(255, 0, 0))
end
```

## Rules when writing scripts

1. **Always check `entity:valid()`** before any entity method call.
2. **Always nil-check** returns from `get_origin()`, `get_velocity()`, `get_angles()`, `get_attachment()`.
3. **Load fonts/images at module level**, never inside callbacks.
4. **Use `game_rules.game_time()`** for game-synced timing, not `os.clock()`.
5. **Use `add_buttonstate1/2` and `clear_buttonstate1/2`** for button manipulation, not direct field writes.
6. **`ignore_callback` in trace functions**: returning `true` means INCLUDE the entity (misleading name).
7. **Render targets**: only useful when content changes less often than every frame.
8. **Particle callback data tables are reused** across handlers in the same frame -- copy fields you need.
9. **No `require()`** -- share via globals, control load order with filename prefixes.
10. **Look up exact signatures** from the docs before using any API function. Do not guess parameter order or types.
