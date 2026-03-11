# Getting Started

## 1. Introduction

Umbrella scripts are plain `.lua` files placed in the `scripts` folder. They run inside a sandboxed **Lua 5.4** environment with access to the Umbrella API -- a set of globals for entities, rendering, menu, tracing, input, and more.

**Key facts:**

- Scripts are loaded **alphabetically** by filename. Use numeric prefixes to control load order (`1_utility.lua` before `2_hero_lib.lua` before `haze.lua`).
- There is no `require()`. Scripts share state through **globals**: a table assigned in one script is accessible in every script loaded after it.
- Each script registers its logic by attaching functions to **callbacks**. There is no return-table export pattern.

## 2. Script Structure

### Minimal Script

The smallest useful script registers a single callback:

```lua
callback.on_frame:set(function()
    -- Runs every frame
end)
```

### Full Skeleton

A typical script creates menu controls at the top level, then registers callbacks that read those controls:

```lua
-- Menu setup (runs once at load time)
local tab = Menu.Create("General", "MySection", "MyTab", "MySubTab")
local group = tab:Create("Settings")
local enabled = group:Switch("Enable", false)
local speed = group:SliderFloat("Speed", 0.0, 100.0, 50.0)

-- Persistent state
local font = Render.LoadFont("Arial", Enum.FontCreate.FONTFLAG_ANTIALIAS)
local last_target = nil

-- Callback: movement logic
local function on_move(cmd)
    if not enabled:Get() then return end
    cmd.forwardmove = speed:Get() / 100.0
end

-- Callback: rendering
local function on_draw()
    if not enabled:Get() then return end
    Render.Text(font, 16, "Active", Vec2(100, 100), Color(0, 255, 0, 255))
end

callback.on_createmove:set(on_move)
callback.on_frame:set(on_draw)
```

### Callback Registration

Register a handler with `:set(fn)` and remove it with `:unset(fn)`:

```lua
local function my_handler()
    -- ...
end

callback.on_frame:set(my_handler)

-- Later, to stop receiving the callback:
callback.on_frame:unset(my_handler)
```

> **Important:** `:unset()` requires the same function reference you passed to `:set()`. Anonymous functions cannot be unregistered.

### Core Callbacks

| Callback | Signature | When |
|----------|-----------|------|
| `on_scripts_loaded` | `fun()` | Once, after all scripts finish loading. |
| `on_createmove` | `fun(cmd: CUserCmd)` | Every tick during movement processing. |
| `on_pre_createmove` | `fun(cmd: CUserCmd)` | Before CreateMove processing. |
| `on_frame` | `fun()` | Every rendered frame. |
| `on_draw` | `fun()` | Every draw frame (after `on_frame`). |
| `on_key_event` | `fun(data): boolean` | On keyboard/mouse input. Return value controls propagation. |
| `on_add_entity` | `fun(ent)` | When an entity enters the entity system. |
| `on_remove_entity` | `fun(ent)` | When an entity leaves the entity system. |

## 3. Working with Entities

### Local Player

```lua
local pawn = entity_list.local_pawn()         -- player_pawn: the in-world character
local controller = entity_list.local_controller() -- entity: the controller
```

### Iterating Entities

`entity_list.by_class_name(name)` returns an array of entities matching the C++ class name:

```lua
local pawns = entity_list.by_class_name("C_CitadelPlayerPawn")
for i = 1, #pawns do
    local pawn = pawns[i]
    if pawn:valid() then
        local pos = pawn:get_origin()
        if pos then
            -- use pos
        end
    end
end
```

### Validity and Nil Guards

Entity pointers can become invalid between frames. **Always** check before use:

```lua
local pawn = entity_list.local_pawn()
if not pawn or not pawn:valid() then return end

-- Position, velocity, and angles return nil when the entity is invalid
local origin = pawn:get_origin()
if not origin then return end
```

### Common Entity Methods

| Method | Returns | Notes |
|--------|---------|-------|
| `entity:valid()` | `boolean` | Must check before any other call. |
| `entity:is_alive()` | `boolean` | |
| `entity:is_dormant()` | `boolean` | Dormant entities are not actively networked. |
| `entity:get_origin()` | `Vector\|nil` | World position. |
| `entity:get_velocity()` | `Vector\|nil` | Local velocity (not world). |
| `entity:get_angles()` | `Angle\|nil` | Rotation angles. |
| `entity:get_max_health()` | `integer` | |
| `entity:get_class_name()` | `string` | C++ class name (e.g. `"C_CitadelPlayerPawn"`). |
| `entity:get_name()` | `string` | Display name. |
| `entity:get_bone_pos(name)` | `Vector\|nil` | Named bone world position. |

### Player Pawn vs Entity

`player_pawn` extends `entity` with player-specific methods. Use `entity_list.local_pawn()` to get it. The polymorphic type system means `entity_list.by_class_name("C_CitadelPlayerPawn")` returns `player_pawn[]`.

### Abilities

Abilities live on the player pawn, looked up by their VData class name:

```lua
local pawn = entity_list.local_pawn()
if not pawn or not pawn:valid() then return end

local dash = pawn:get_ability("citadel_ability_dash")
if dash and dash:valid() then
    -- Access ability fields via raw struct:
    local cooldown = dash.m_flCooldownEnd
end

-- All abilities:
local abilities = pawn:get_abilities()
for i = 1, #abilities do
    local ab = abilities[i]
    -- ...
end
```

### Modifiers

Modifiers represent buffs, debuffs, and status effects on an entity:

```lua
local pawn = entity_list.local_pawn()
if not pawn or not pawn:valid() then return end

-- Check by name
if pawn:has_modifier("modifier_stunned") then
    -- stunned
end

-- Get a specific modifier
local mod = pawn:get_modifier("modifier_sprint")
if mod then
    local remaining = mod:get_remaining_time()
end

-- Iterate all modifiers
local mods = pawn:get_modifiers()
for i = 1, #mods do
    local m = mods[i]
    -- m:get_name(), m:get_remaining_time(), m:get_ability(), etc.
end
```

## 4. Menu System

### Creating Tabs and Groups

The menu is built with a fluent builder pattern. `Menu.Create()` accepts up to 5 path segments and returns the deepest node:

```lua
-- Create a tab hierarchy: General > Combat > Aimbot > Settings
local group = Menu.Create("General", "Combat", "Aimbot", "Settings")
-- 'group' is a CMenuGroup you can add widgets to
```

To create intermediate nodes separately:

```lua
local tab = Menu.Create("General", "Combat", "Aimbot", "Settings")
local group = tab:Create("Targeting")
```

### Widget Types

```lua
-- Toggle switch (default: off)
local enabled = group:Switch("Enable", false)

-- Key bind
local key = group:Bind("Hotkey", 0)

-- Float slider (min, max, default)
local speed = group:SliderFloat("Speed", 0.0, 10.0, 5.0)

-- Integer slider
local count = group:SliderInt("Count", 1, 10, 3)

-- Dropdown
local mode = group:ComboBox("Mode", {"Off", "Legit", "Rage"}, 0)

-- Color picker
local color = group:ColorPicker("Highlight", Color(255, 0, 0, 255))

-- Button
local btn = group:Button("Reset", function()
    -- on click
end)
```

### Reading Values

All widgets expose `:Get()`:

```lua
if enabled:Get() then
    local spd = speed:Get()        -- number
    local idx = mode:Get()          -- integer index
    local col = color:Get()         -- Color
end
```

### Conditional Visibility

Show or hide widgets based on the state of another widget:

```lua
local master = group:Switch("Enable Feature", false)
local detail = group:SliderFloat("Intensity", 0.0, 1.0, 0.5)

-- 'detail' only visible when 'master' is on
detail:SetVisibility(master)
```

## 5. Rendering

### Loading Resources

Load fonts and images **once** at the top level (not inside a callback):

```lua
local font = Render.LoadFont("Arial", Enum.FontCreate.FONTFLAG_ANTIALIAS)
local icon = Render.LoadImage("path/to/icon.png")
```

### Drawing Primitives

All draw calls must happen inside `on_frame` or `on_draw`:

```lua
callback.on_frame:set(function()
    -- Text
    Render.Text(font, 16, "Hello", Vec2(100, 100), Color(255, 255, 255, 255))

    -- Filled rectangle with rounded corners
    Render.FilledRect(Vec2(10, 10), Vec2(200, 50), Color(0, 0, 0, 150), 5)

    -- Unfilled rectangle
    Render.Rect(Vec2(10, 10), Vec2(200, 50), Color(255, 255, 255, 200), 5)

    -- Line
    Render.Line(Vec2(0, 0), Vec2(100, 100), Color(255, 0, 0, 255), 2)

    -- Filled circle
    Render.FilledCircle(Vec2(300, 300), 25, Color(0, 255, 0, 200))

    -- Circle outline
    Render.Circle(Vec2(300, 300), 30, Color(255, 255, 0, 255), 2)
end)
```

### WorldToScreen

Convert 3D world positions to 2D screen coordinates for in-game overlays:

```lua
callback.on_frame:set(function()
    local pawn = entity_list.local_pawn()
    if not pawn or not pawn:valid() then return end

    local origin = pawn:get_origin()
    if not origin then return end

    local screen_pos, visible = Render.WorldToScreen(origin)
    if visible then
        Render.Text(font, 14, "Here", screen_pos, Color(255, 255, 255, 255))
    end
end)
```

### Clipping

Restrict draw calls to a rectangular region:

```lua
callback.on_frame:set(function()
    Render.PushClip(Vec2(50, 50), Vec2(300, 200))
    -- Everything drawn here is clipped to the 50,50 -> 300,200 rectangle
    Render.Text(font, 14, "Clipped text", Vec2(60, 60), Color(255, 255, 255, 255))
    Render.PopClip()
end)
```

## 6. Render Target Optimization

### The Problem

Every `Render.Text`, `Render.FilledRect`, etc. inside `on_frame` executes **every frame** (typically 60-300+ FPS). Complex HUD overlays with many draw calls become a performance bottleneck. If your overlay only changes when game state changes (new target acquired, health threshold crossed, timer expired), most of those draw calls are wasted -- redrawing identical pixels.

### The Solution: Render Targets

A **render target** (RT) is an off-screen texture you draw into once, then blit to screen cheaply every frame. The workflow:

1. **Allocate** the RT once at load time with `Render.FindOrCreateRT`.
2. **Draw into** the RT with `Render.RenderToRT` only when content changes.
3. **Blit** the cached RT to screen every frame with `Render.DrawRT` (a single texture copy, very cheap).

### The Dirty-Flag Pattern

Track whether the RT content is stale. Only re-render when something changes:

```lua
-- Allocate once at load time
local hud_rt = Render.FindOrCreateRT("my_hud_overlay", 400, 200)
local rt_dirty = true  -- Force initial draw

local font = Render.LoadFont("Arial", Enum.FontCreate.FONTFLAG_ANTIALIAS)
local cached_health = -1
local cached_target_name = ""

-- Mark dirty when relevant state changes
local function update_state()
    local pawn = entity_list.local_pawn()
    if not pawn or not pawn:valid() then return end

    local origin = pawn:get_origin()
    if not origin then return end

    local health = pawn:get_max_health()
    if health ~= cached_health then
        cached_health = health
        rt_dirty = true
    end
end

-- Draw the HUD content into the RT coordinate space
local function draw_hud_content()
    -- RT coordinate space starts at Vec2(0, 0), size is 400x200
    Render.FilledRect(Vec2(0, 0), Vec2(400, 200), Color(20, 20, 20, 200), 8)
    Render.Rect(Vec2(0, 0), Vec2(400, 200), Color(100, 100, 100, 255), 8)
    Render.Text(font, 16, "Health: " .. tostring(cached_health), Vec2(10, 10), Color(255, 255, 255, 255))
    Render.Text(font, 14, "Target: " .. cached_target_name, Vec2(10, 40), Color(200, 200, 200, 255))
end

-- Screen position where the HUD appears
local hud_pos = Vec2(50, 400)

callback.on_frame:set(function()
    update_state()

    -- Only re-render the RT when state changed
    if rt_dirty then
        rt_dirty = false
        Render.RenderToRT(hud_rt, function()
            draw_hud_content()
        end)
    end

    -- Blit the cached texture every frame (single draw call)
    Render.DrawRT(hud_rt, hud_pos, Color(255, 255, 255, 255))
end)
```

### Coordinate Space

Inside `Render.RenderToRT`, the coordinate system is **local to the RT**. The top-left corner is `Vec2(0, 0)` and the bottom-right is `Vec2(width, height)` of the RT. The screen position is only relevant when you call `Render.DrawRT`.

### When to Use Render Targets

**Good candidates:**

- Static or rarely-changing HUD panels (scoreboard, dashboard, info overlays)
- Decorative elements that only update on events (kill feed, timer display)
- Complex multi-element panels where the composition is expensive

**Bad candidates:**

- Health bars or cooldown indicators that change every frame -- the RT would be re-rendered every frame anyway, adding overhead instead of saving it
- Single draw calls -- the overhead of RT management exceeds the cost of one `Render.Text`

The rule: if your content changes less often than every frame, an RT saves work. If it changes every frame, draw directly.

## 7. Tracing and Raycasting

### trace.line

Cast a ray between two world positions and check what it hits:

```lua
local pawn = entity_list.local_pawn()
if not pawn or not pawn:valid() then return end

local eye_pos = pawn:get_origin()
if not eye_pos then return end

local target_pos = Vector(1000, 500, 100)

local result = trace.line(
    eye_pos,
    target_pos,
    Enum.TraceContentMask.TRACE_MASK_VISIBLE,  -- content mask
    nil,   -- exclude
    nil,   -- as
    nil,   -- object_set_mask (overridden internally)
    nil,   -- collision_group
    function(ent)
        return true  -- INCLUDE this entity in results
    end
)

if result.fraction < 1.0 then
    -- Hit something before reaching target_pos
    local hit_ent = result:hit_entity()
end
```

### trace.hull

A hull trace sweeps a box instead of a thin ray -- useful for wider collision checks:

```lua
local result = trace.hull(
    start_pos,
    end_pos,
    Vector(-16, -16, 0),   -- hull min bounds
    Vector(16, 16, 72),    -- hull max bounds
    Enum.TraceContentMask.TRACE_MASK_VISIBLE,
    nil, nil, nil, nil,
    function(ent) return true end,
    true  -- ignore_local: exclude local player
)
```

### trace.bullet

Check if a bullet would hit a specific entity:

```lua
local would_hit = trace.bullet(eye_pos, target_pos, 1.0, target_ent)
if would_hit then
    -- Bullet path is clear to target
end
```

### The ignore_callback Gotcha

The `ignore_callback` parameter name is misleading. Despite the name:

- **Return `true`** to **INCLUDE** the entity in trace results (it will block the ray).
- **Return `false`** to **EXCLUDE** the entity (the ray passes through it).

```lua
-- Only trace against player pawns, ignore everything else
local result = trace.line(start, end_pos,
    Enum.TraceContentMask.TRACE_MASK_VISIBLE,
    nil, nil, nil, nil,
    function(ent)
        -- true = INCLUDE (entity blocks the ray)
        -- false = EXCLUDE (ray passes through)
        return ent:get_class_name() == "C_CitadelPlayerPawn"
    end
)
```

### Checking Results

The `fraction` field tells you how far along the ray the hit occurred:

| Value | Meaning |
|-------|---------|
| `1.0` | No hit -- ray traveled full distance. |
| `0.0` | Hit at the very start. |
| `0.0 < f < 1.0` | Hit partway through. |

```lua
if result.fraction < 1.0 then
    local hit = result:hit_entity()
    local hitbox = result:hitbox_name()
    local is_floor = result:is_vertical_normal()
end
```

## 8. Movement and Input

### CUserCmd

The `on_createmove` callback receives a `CUserCmd` -- the input command sent to the server each tick. You can read and modify it:

```lua
callback.on_createmove:set(function(cmd)
    -- Movement values range -1.0 to 1.0
    cmd.forwardmove = 1.0   -- full forward
    cmd.leftmove = 0.0      -- no strafe

    -- Read current view angles
    local angles = cmd.viewangles  -- Angle
end)
```

### Button State

Use the synced methods to manipulate button state (these keep the struct and protobuf in sync):

```lua
callback.on_createmove:set(function(cmd)
    -- Press jump
    cmd:add_buttonstate1(InputBitMask_t.IN_JUMP)
    cmd:add_buttonstate2(InputBitMask_t.IN_JUMP)

    -- Release a button
    cmd:clear_buttonstate1(InputBitMask_t.IN_ATTACK)
    cmd:clear_buttonstate2(InputBitMask_t.IN_ATTACK)
end)
```

> **Warning:** Writing to `cmd.button_state0/1/2` directly only updates the struct, not the protobuf. Always use `add_buttonstate*` / `clear_buttonstate*` to stay in sync.

### Smooth Aiming

Interpolate the camera toward a target angle with humanized smoothing:

```lua
callback.on_createmove:set(function(cmd)
    local target_angle = Angle(10.0, 45.0, 0.0)
    local smooth_factor = 10.0  -- minimum is 5.0 internally

    cmd:smooth_aim(target_angle, smooth_factor)
end)
```

### Psilent Aim

Move the camera position to aim at a target without visible camera movement:

```lua
callback.on_createmove:set(function(cmd)
    local target_pos = target_ent:get_origin()
    if not target_pos then return end

    if cmd:can_psilent_at_pos(target_pos) then
        cmd:set_psilent_at_pos(target_pos)
    end
end)
```

## 9. Tips and Best Practices

### Defensive Coding

```lua
-- WRONG: crashes if pawn is invalid or origin is nil
local pos = entity_list.local_pawn():get_origin()

-- RIGHT: guard every step
local pawn = entity_list.local_pawn()
if not pawn or not pawn:valid() then return end
local pos = pawn:get_origin()
if not pos then return end
```

Methods that return `nil` on invalid state: `get_origin()`, `get_velocity()`, `get_angles()`, `get_bone_pos()`, `get_attachment()`. Always nil-check.

### Timing

Use `game_rules.game_time()` for game-synchronized timing instead of `os.clock()`:

```lua
local last_action_time = 0

callback.on_createmove:set(function(cmd)
    local now = game_rules.game_time()
    if now - last_action_time < 0.5 then return end  -- 500ms cooldown
    last_action_time = now
    -- ...
end)
```

### Performance

- **Avoid heavy work in `on_frame`.** It runs every rendered frame. Move logic to `on_createmove` (tick-rate) or event callbacks when possible.
- **Use Render Targets** for static or slowly-changing HUD elements (see Section 6).
- **Cache entity lookups.** `entity_list.by_class_name()` scans the entity list each call. Store results when appropriate, but re-validate with `entity:valid()` before use.

### Script Organization

Use numbered prefixes for library scripts that other scripts depend on:

```
scripts/
  1_globals.lua      -- shared utilities, loaded first
  2_target_lib.lua   -- targeting helpers
  3_render_lib.lua   -- drawing helpers
  haze.lua           -- hero-specific script
  shiv.lua           -- hero-specific script
```

Since there is no `require()`, library scripts expose their API through globals:

```lua
-- In 1_globals.lua:
utils = {}

function utils.distance(a, b)
    local dx = a.x - b.x
    local dy = a.y - b.y
    local dz = a.z - b.z
    return math.sqrt(dx * dx + dy * dy + dz * dz)
end

-- In haze.lua (loaded later):
local dist = utils.distance(my_pos, target_pos)
```

### Common Mistakes

1. **Forgetting `entity:valid()` checks.** Entity pointers go stale between frames. Always validate.
2. **Treating `ignore_callback` return value as "ignore".** `true` means INCLUDE, `false` means EXCLUDE.
3. **Loading fonts/images inside callbacks.** `Render.LoadFont` and `Render.LoadImage` allocate resources -- call them once at script load, not every frame.
4. **Writing to `button_state` fields directly.** Use `add_buttonstate*`/`clear_buttonstate*` methods to keep struct and protobuf in sync.
5. **Assuming `get_origin()` always returns a Vector.** It returns `nil` when the entity's scene node is invalid.
