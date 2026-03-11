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
| NEW_UI_LIB (high-level menu wrapper with groups, elements, gears) | `skill://deadlock-lua/docs/new-ui-lib.md` |
| HERO_LIB (state checks, target finding, ability/item casting, projectile prediction, movement) | `skill://deadlock-lua/docs/hero-lib.md` |
| LIB_RENDER (render wrappers, animations, hitbox/button system, image/font caching) | `skill://deadlock-lua/docs/render-lib.md` |
| Ability diagnostics (VData fields, targeting types, casting patterns) | See "Diagnosing ability behavior" section below |

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

## Diagnosing ability behavior (MCP bridge)

When writing a hero combo script for an unfamiliar ability, **do NOT guess** the cast type.
Use the MCP bridge tools to inspect the ability at runtime before writing any handling code.

### Step 1: Get ability names
```lua
local pawn = entity_list.local_pawn()
local abilities = pawn:get_abilities()
for i, ab in ipairs(abilities) do
    if ab and ab:valid() then
        print(string.format("[%d] %s", i, ab:get_name()))
    end
end
```

### Step 2: Read VData targeting fields
These fields on the ability VData determine HOW the ability targets and casts:
```lua
local ab = pawn:get_ability("ability_name_here")
local vdata = ab:get_vdata()
-- Key fields:
vdata.m_eAbilityType            -- 1=active, 2=ultimate
vdata.m_eAbilityActivation      -- activation mode
vdata.m_eAbilityTargetingShape  -- 0=point/projectile, 2=directional/cone
vdata.m_flTargetingConeAngle    -- if 0, ability has NO cone → don't use is_target_within_cone
vdata.m_flTargetingConeHalfWidth
vdata.m_nAbilityTargetTypes     -- bitmask of valid target types
```

### Step 3: Read ability-specific class fields
Use `lookup_class` on the SDK class to find state fields:
- `m_nCurrentLungeState`, `m_eUltState` → ability has state machine
- `m_vDashDirection` → directional dash (aim at target, then cast)
- `m_vCastPosition`, `m_qCastAngles` → stores cast location
- `m_bInCastDelay`, `m_bChanneling` → standard cast state

### Step 4: Choose the casting pattern

| VData shape | Cone angle | Pattern |
|-------------|-----------|---------|
| 0 (point) + has projectileInfo | N/A | Projectile prediction: `predict_projectile_simulated` + `hull_projectile_will_hit` + `aim_psilent_default` with `cast_ability` in callback |
| 0 (point) + no projectile | > 0 | Cone check: `is_target_within_cone` + buttonstate or `cast_ability` |
| 2 (directional) | 0 | **FOV-based**: `is_target_within_fov` + `cast_ability`. Do NOT use `is_target_within_cone` (always fails with cone=0) |
| 2 (directional) | > 0 | Cone check works: `is_target_within_cone` + `cast_ability` |
| Any | N/A | Self-cast / no-target: just `cast_ability` directly |

### Common mistake
`HERO_LIB.is_target_within_cone` reads `m_flTargetingConeAngle` from VData. If it's 0, the function
will always return false. For directional abilities with 0 cone angle, use `is_target_within_fov`
to check if the target is roughly in front of you, then `HERO_LIB.cast_ability()` to fire.

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

## Library scripts (loaded via numeric prefix)

These libraries are loaded before hero scripts and provide shared utilities.

### NEW_UI_LIB (1_new_ui_lib.lua)
High-level menu wrapper with automatic visibility/disable chaining.
```lua
-- Create a menu tab and group
local tab = NEW_UI_LIB.create_tab(false, Menu.Find("Heroes"), "My Section")
local group = tab:create("Settings")

-- Add widgets to group -- all return chainable ui_lib_element
local enabled = group:switch("Enable", true, "\u{f00c}")
local speed = group:slider("Speed", 0.0, 100.0, 50.0, "%.1f", "\u{f3fd}")
local mode = group:combo("Mode", {"Safe", "Aggressive"}, 1, "\u{f201}")

-- Chain visibility: speed slider disabled unless enabled is on
speed:link_to_ui_disable_condition(enabled)

-- Read values via callable syntax
if enabled() then
    local spd = speed()           -- number
    local is_safe = mode("Safe")  -- true/false by name
end
```

### HERO_LIB (2_hero_lib.lua)
Hero utilities: state checks, target finding, ability casting, projectile prediction.
```lua
-- Always available via global HERO_LIB after load
local lp = HERO_LIB.lp  -- cached local pawn (updated each tick)

-- State checks
if HERO_LIB.is_stunned(target) or HERO_LIB.is_invulnerable(target) then return end

-- Find combo target (respects UI settings + per-hero overrides)
local target = HERO_LIB.find_combo_target(cmd, lp)

-- Ability helpers
local ability = lp:get_ability("ability_sleep_dagger")
if ability and HERO_LIB.is_ability_ready(ability) then
    HERO_LIB.cast_ability(cmd, lp, ability, false, false)
end

-- Projectile prediction (simulated)
local aim_pos, predicted_pos = HERO_LIB.predict_projectile_simulated(
    false, HERO_LIB.ENUM_PPS_INFO_FROM.PROJECTILE,
    HERO_LIB.ENUM_MV_SIM_TYPE.SIMULATE_MOVEMENT,
    HERO_LIB.ENUM_PPS_AIM_TO_POS.LIB_TARGET_POS,
    target, ability
)

-- Item handling (uses menu multiselects)
HERO_LIB.handle_all_items(cmd, lp, target,
    items_enabled, items_smooth, items_psilent,
    aoe_widget, target_widget, non_target_widget)
```

### LIB_RENDER (3_render_lib.lua)
Render wrappers with caching, animations, and custom hitbox/button system.
```lua
-- Font loading (cached)
local my_font = LIB_RENDER.font("Arial", {"FONTFLAG_ANTIALIAS"})

-- Drawing (wraps Render API)
LIB_RENDER.filled_rect(pos, pos + size, Color(20, 20, 20, 200), 5)
LIB_RENDER.text(my_font, 14, pos, "Hello", Color(255), {true, false})
LIB_RENDER.image("panorama/images/heroes/haze_mm_psd.vtex_c", pos, Vec2(32, 32), true, Color(255))

-- Smooth animations
local alpha = LIB_RENDER.calculate_value("my_fade", is_active, 2.0, 0, 1)
alpha = LIB_RENDER.easings["out_quart"](alpha)

-- Draggable hitbox (custom UI)
local drag = LIB_RENDER.drag_hitbox(pos, size, function(el)
    -- called while dragging; el.pos_1 is updated position
end)

-- Button hitbox (toggleable)
local btn = LIB_RENDER.button_hitbox(pos, pos + size, false, nil, function(el)
    -- el.value is toggled on click
end)
```
