# Input & Commands

## CUserCmd

User input command sent to the server each tick.

### Fields

| Name | Type | Description |
|------|------|-------------|
| `legacy_command_number` | `integer` | Legacy command sequence number. |
| `client_tick` | `integer` | Client tick when command was created. |
| `viewangles` | `Angle` | View direction angles. |
| `forwardmove` | `number` | Forward/backward movement input (-1.0 to 1.0). |
| `leftmove` | `number` | Left/right strafe movement input (-1.0 to 1.0). |
| `upmove` | `number` | Up/down movement input. |
| `impulse` | `number` | Impulse command value. |
| `weaponselect` | `integer` | Selected weapon index. |
| `random_seed` | `integer` | Random seed for this command. |
| `mousedx` | `integer` | Mouse delta X (horizontal movement). |
| `mousedy` | `integer` | Mouse delta Y (vertical movement). |
| `pawn_entity_handle` | `integer` | Entity handle of the controlled pawn. |
| `consumed_server_angle_changes` | `integer` | Number of consumed server angle changes. |
| `cmd_flags` | `integer` | Command flags bitmask. |
| `vec_camera_position` | `Vector` | Current camera world position. |
| `ang_camera_angles` | `Angle` | Current camera angles. |
| `execute_ability_indices` | `integer` | Ability index to execute. |
| `in_shop` | `boolean` | Whether the shop UI is open. |
| `camera_roaming_speed` | `number` | Camera roaming speed. |
| `using_free_cursor` | `boolean` | Whether free cursor mode is active. |
| `enemy_hero_aimed_at` | `integer` | Entity handle of the enemy hero being aimed at. |
| `button_state0` | `InputBitMask_t\|integer` | Raw button state slot 0. Writes ONLY to struct, not protobuf. Use add_/clear_/set_input to stay in sync. |
| `button_state1` | `InputBitMask_t\|integer` | Raw button state slot 1. Same caveat as button_state0. |
| `button_state2` | `InputBitMask_t\|integer` | Raw button state slot 2. Same caveat as button_state0. |
| `orig_vec_camera_position` | `Vector` | Read-only. Original camera position before callbacks. |
| `orig_ang_camera_angles` | `Angle` | Read-only. Original camera angles before callbacks. |

### Methods

#### `CUserCmd:add_buttonstate1(bit_mask)`

Adds bits to button state 1. Keeps struct and protobuf in sync.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `bit_mask` | `InputBitMask_t\|integer` | Button bits to set. |

#### `CUserCmd:add_buttonstate2(bit_mask)`

Adds bits to button state 2. Keeps struct and protobuf in sync.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `bit_mask` | `InputBitMask_t\|integer` | Button bits to set. |

#### `CUserCmd:add_buttonstate3(bit_mask)`

Adds bits to button state 3. Keeps struct and protobuf in sync.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `bit_mask` | `InputBitMask_t\|integer` | Button bits to set. |

#### `CUserCmd:clear_buttonstate1(bit_mask)`

Clears bits from button state 1. Keeps struct and protobuf in sync.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `bit_mask` | `InputBitMask_t\|integer` | Button bits to clear. |

#### `CUserCmd:clear_buttonstate2(bit_mask)`

Clears bits from button state 2. Keeps struct and protobuf in sync.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `bit_mask` | `InputBitMask_t\|integer` | Button bits to clear. |

#### `CUserCmd:clear_buttonstate3(bit_mask)`

Clears bits from button state 3. Keeps struct and protobuf in sync.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `bit_mask` | `InputBitMask_t\|integer` | Button bits to clear. |

#### `CUserCmd:get_psilent_camera_pos(target_pos)`

Computes the camera position needed for psilent aim at the target.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `target_pos` | `Vector` | World position of the target. |

**Returns:** `Vector` — Camera position that would aim at target_pos psilently.

#### `CUserCmd:can_psilent_at_pos(target_pos)`

Checks if psilent aim is possible at the given world position.
Validates: not camera snapping, delta bounds (100/80/80), local pawn exists, distance < 170 units.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `target_pos` | `Vector` | World position to test. |

**Returns:** `boolean` — True if psilent aim is feasible this tick.

#### `CUserCmd:set_psilent_at_pos(target_pos)`

Applies psilent aim toward the target position.
Does NOT internally validate — caller must call `can_psilent_at_pos` first.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `target_pos` | `Vector` | World position to aim at psilently. |

#### `CUserCmd:smooth_aim(aim_angle, smooth)`

Smoothly interpolates camera toward the target angle using humanized smoothing (minimum 5.0).
No-op during camera snap. Writes to game camera only, NOT the protobuf field.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `aim_angle` | `Angle` | Target angle to interpolate toward. |
| `smooth` | `number` | Smoothing factor (clamped to minimum 5.0 internally). |

#### `CUserCmd:reset_backtrack()`

Resets backtrack state. Always operates on the global current command; self is ignored.

#### `CUserCmd:reset_camera_pos()`

Restores the protobuf camera position to its original value. No-op during camera snap.

#### `CUserCmd:reset_camera_ang()`

Restores both protobuf angles and live game camera angles to their original values. No-op during camera snap.

#### `CUserCmd:get_orig_button_state0()`

Returns the frame-start snapshot of button state 0 (before any callbacks ran).

**Returns:** `InputBitMask_t|integer` — Original button state 0.

#### `CUserCmd:get_orig_button_state1()`

Returns the frame-start snapshot of button state 1 (before any callbacks ran).

**Returns:** `InputBitMask_t|integer` — Original button state 1.

#### `CUserCmd:get_orig_button_state2()`

Returns the frame-start snapshot of button state 2 (before any callbacks ran).

**Returns:** `InputBitMask_t|integer` — Original button state 2.

#### `CUserCmd:set_input(mask, type)`

Encodes EInButtonState bits across buttonstate1/2/3 (both struct and protobuf).

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `mask` | `InputBitMask_t\|integer` | Button mask to set. |
| `type` | `integer` | EInButtonState type. |

## input

Raw input interface.

### Methods

#### `input.cursor_pos()`

Returns current cursor screen position.

**Returns:** `Vec2`

#### `input.cursor_in_bounds(start, end_)`

Returns whether cursor is within the specified rectangle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `start` | `Vec2` | Top-left corner of the bounding rectangle. |
| `end_` | `Vec2` | Bottom-right corner of the bounding rectangle. |

**Returns:** `boolean`

#### `input.is_down(key)`

Returns whether the specified key is currently held down.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `key` | `Enum.ButtonCode` | Key to check. |

**Returns:** `boolean`

#### `input.is_pressed(key)`

Returns whether the specified key was just pressed this frame.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `key` | `Enum.ButtonCode` | Key to check. |

**Returns:** `boolean`

## convar_table

Console variable accessor. Indexed by cvar name string (e.g., `convar.sv_cheats`).
Each accessor supports dual get/set pattern: call with no args to get, with arg to set.
Returns nil if the CVar engine is unavailable.

### Methods

#### `convar_table:float()`

Gets or sets the float value of this convar.

**Returns:** `number|nil`

**Overloads:**

- `fun(self: convar_table, val: number)`

#### `convar_table:bool()`

Gets or sets the boolean value of this convar.

**Returns:** `boolean|nil`

**Overloads:**

- `fun(self: convar_table, val: boolean): nil`

#### `convar_table:int()`

Gets or sets the integer value of this convar.

**Returns:** `integer|nil`

**Overloads:**

- `fun(self: convar_table, val: integer)`

### `convar`

**Type:** `table<string, convar_table>`
