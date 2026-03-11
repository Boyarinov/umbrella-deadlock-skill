# Utilities

## utils

Utility functions for camera, targeting, geometry, and map operations.

### Methods

#### `utils.set_camera_angles(angle)`

Sets the game camera angles.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `angle` | `Angle` | New camera angles to apply. |

#### `utils.get_camera_angles()`

Returns the current game camera angles.

**Returns:** `Angle` — Current camera angles.

#### `utils.get_camera_pos()`

Returns the current game camera world position.

**Returns:** `Vector` — Current camera position in world space.

#### `utils.get_camera_fov()`

Returns the current camera field of view in degrees.

**Returns:** `number` — FOV in degrees.

#### `utils.fov_to_pixel_radius(fov)`

Converts a FOV angle to a pixel radius on screen.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `fov` | `number` | FOV angle in degrees. |

**Returns:** `number` — Corresponding pixel radius.

#### `utils.find_nearest_visible_enemy()`

Finds the nearest enemy player pawn that is currently visible.
Performs a visibility check; returns nil if no visible enemy is found.

**Returns:** `player_pawn|nil` — Nearest visible enemy pawn, or nil if none.

#### `utils.find_target_in_fov(fov)`

Finds the best target within the specified FOV cone.
Performs per-bone scanning with a 3.0-degree tie-breaking threshold.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `fov` | `number` | Maximum FOV cone angle in degrees. |

**Returns:** `player_pawn|nil` — Best target within FOV, or nil if none.

#### `utils.find_nearest_fov_enemy()`

Finds the nearest enemy by angular (FOV) distance.
Does NOT require visibility — no visibility check is performed.

**Returns:** `player_pawn|nil` — Nearest enemy by FOV distance, or nil if none.

#### `utils.calc_angle(src, dst)`

Calculates the angle from a source position to a destination position.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `src` | `Vector` | Source world position. |
| `dst` | `Vector` | Destination world position. |

**Returns:** `Angle` — Angle pointing from src toward dst.

#### `utils.get_fov(src, dst)`

Calculates the FOV difference between two angles in degrees.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `src` | `Angle` | Source angle. |
| `dst` | `Angle` | Destination angle. |

**Returns:** `number` — Angular difference in degrees.

#### `utils.angle_diff(dst, src)`

Calculates the shortest angular difference between two angles.
Result is normalized to the shortest path (handles wrap-around).

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `dst` | `number` | Destination angle in degrees. |
| `src` | `number` | Source angle in degrees. |

**Returns:** `number` — Shortest angular difference in degrees.

#### `utils.predict_bullet(src, dst, target_velocity, primary_weapon, shooter?)`

Predicts bullet destination accounting for projectile travel time.
Uses the weapon's projectile speed to compensate for target velocity.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `src` | `Vector` | Shooter position. |
| `dst` | `Vector` | Current target position. |
| `target_velocity` | `Vector` | Target's current velocity. |
| `primary_weapon` | `ability` | Primary weapon entity used for projectile speed. |
| `shooter` *(optional)* | `entity` | Default: `local pawn`. Entity used as shooter origin; defaults to local player pawn. |

**Returns:** `Vector` — Predicted impact position.

#### `utils.get_slide_level()`

Returns the current slide charge level.

**Returns:** `integer` — Slide level (0 = no slide).

#### `utils.get_slide_angle()`

Returns the current slide angle in degrees.

**Returns:** `number` — Slide angle.

#### `utils.is_line_intersect_entity(start, end_, ent)`

Tests if a line segment intersects an entity's bounding box.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `start` | `Vector` | Line start position. |
| `end_` | `Vector` | Line end position. |
| `ent` | `entity` | Target entity. |

**Returns:** `boolean` — True if the line intersects the entity's bounding box.

#### `utils.is_hull_intersect_entity(start, end_, hull_radius, ent, ent_origin_offset)`

Tests if a hull (capsule) from start to end_ intersects with an entity.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `start` | `Vector` | Hull start position. |
| `end_` | `Vector` | Hull end position. |
| `hull_radius` | `number` | Hull radius. |
| `ent` | `entity` | Target entity. |
| `ent_origin_offset` | `Vector` | Offset applied to entity origin. |

**Returns:** `boolean` — True if the hull intersects the entity.

#### `utils.get_line_intersection_entity(start, end_, ent)`

Returns the intersection point of a line with an entity.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `start` | `Vector` | Line start position. |
| `end_` | `Vector` | Line end position. |
| `ent` | `entity` | Target entity. |

**Returns:** `Vector` — World position of the intersection point.

#### `utils.world_to_map(pos, is_inverted?)`

Converts a world position to minimap coordinates.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pos` | `Vector` | World position to convert. |
| `is_inverted` *(optional)* | `boolean` | Default: `false`. Whether to invert the mapping. |

**Returns:** `Vec2` — Minimap coordinates.

#### `utils.minimap_to_world(pos, is_inverted?)`

Converts minimap coordinates to world position.
WARNING: `is_inverted=false` behaves identically to `true` due to a bug in optional parameter testing.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pos` | `Vec2` | Minimap coordinates to convert. |
| `is_inverted` *(optional)* | `boolean` | Default: `false`. Whether to invert the mapping (see warning). |

**Returns:** `Vec2` — World position.

#### `utils.minimap_percent_to_minimap(pos, is_inverted?)`

Converts minimap percentage coordinates to minimap pixel coordinates.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pos` | `Vec2` | Minimap position as percentage (0.0–1.0 range). |
| `is_inverted` *(optional)* | `boolean` | Default: `false`. Whether to invert the mapping. |

**Returns:** `Vec2` — Minimap pixel coordinates.

#### `utils.get_neutral_camps(team_num, all_types?)`

Returns neutral camp info for the given team.
IMPORTANT: Returns ONLY camps with NO live entity in the entity system (dead or hidden camps).

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `team_num` | `integer` | Team number to query. |
| `all_types` *(optional)* | `boolean` | Default: `false`. If true, include all camp types instead of filtering. |

**Returns:** `camp_info[]` — Array of camp info entries for dead/hidden camps.

#### `utils.execute_command(cmd)`

Executes a console command.
Silent no-op if CInputService is unavailable.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `cmd` | `string` | Console command string to execute. |

## camp_info

Neutral camp information returned by `utils.get_neutral_camps`.

### Fields

| Name | Type | Description |
|------|------|-------------|
| `pos_x` | `number` | Camp X position on minimap. |
| `pos_y` | `number` | Camp Y position on minimap. |
| `name` | `string` | Camp identifier name. |
| `visible` | `string` | Camp visibility state. |
| `type` | `integer` | Camp type identifier. |

## db

Persistent key-value store. Automatically saved to `db.json` on save or every 5 minutes.
Supports metamethods:
- `db.key = value` — Set a value (`__newindex`).
- `local v = db.key` — Get a value (`__index`).
- `db.key = nil` — Delete an entry.
- `#db` — Returns the number of entries (`__len`).
- `tostring(db)` — Returns JSON representation (`__tostring`).
Storable types: `boolean`, `number` (stored as float), `string`, `Vec2`, `Color`, `Vector`.
Lua tables are recursively converted to nested db subtrees.
Unsupported value types are silently dropped (no error).
Keys must be `string` or `number`. Numeric string keys auto-convert to integer indices.

### Indexing

- `[string]`: `boolean|number|string|Vec2|Color|Vector|db` — 
- `[integer]`: `boolean|number|string|Vec2|Color|Vector|db` — 

### Methods

#### `db:to_table()`

Deep-converts the db tree to plain Lua tables.

**Returns:** `table`

### `global_ctx_t`

**Type:** `table<string, string|number|boolean>`

Cross-script shared state (session-only, lost on reload).
Get (`__index`): tries string, then float, then bool (in that order), returns first match or nil.
Set (`__newindex`): accepts string, number (stored as float), boolean. Other types are silently ignored (logged to engine, not Lua error).
Keys must be strings. Non-string keys are silently ignored.
No persistence — values are lost on script reload.

## meta

Meta tracker API for hero/item statistics.

### Methods

#### `meta.get(period, rank)`

Returns meta data for the given period and rank.
Throws on hard errors. Returns nil when data is not yet available (still loading).

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `period` | `integer` | Time period filter. |
| `rank` | `integer` | Rank filter. |

**Returns:** `table|nil`

#### `meta.ready()`

Returns whether meta data has finished loading and is available.

**Returns:** `boolean`

#### `meta.failed()`

Returns whether meta data loading has failed.

**Returns:** `boolean`

## net_channel

Network channel interface.

### Methods

#### `net_channel.latency()`

Returns outgoing flow latency in seconds. Returns 0.0 if net channel is unavailable.

**Returns:** `number` — Outgoing latency in seconds, or 0.0 if the channel is unavailable.

## global_vars

Engine timing and frame information.

### Methods

#### `global_vars.interval_per_tick()`

Returns seconds per tick.

**Returns:** `number`

#### `global_vars.tickcount()`

Returns current tick number.

**Returns:** `integer`

#### `global_vars.curtime()`

Returns current time in seconds.

**Returns:** `number`

#### `global_vars.framecount()`

Returns current frame number.

**Returns:** `integer`

#### `global_vars.absoluteframetime()`

Returns time elapsed since last frame in seconds.

**Returns:** `number`

## game_rules

Game rules interface.

### Methods

#### `game_rules.get()`

Returns C_CitadelGameRules as raw_struct for schema field access.

**Returns:** `raw_struct`

#### `game_rules.game_time()`

Returns current game time in seconds.

**Returns:** `number`

#### `game_rules.match_id()`

Returns the current match ID. Returns 0 if Game Coordinator is not ready.

**Returns:** `integer`

### `GameLocalizer.Find(token)`

Returns localized string by token or returns empty string if token not found.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `token` | `string` | should be in format `#token` |

**Returns:** `string`

### `Localizer.Get(str)`

Returns localized string using current language.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `str` | `string` |  |

**Returns:** `string`

### `Localizer.RegToken(str)`

Registers key (token) string to localizer.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `str` | `string` |  |

**Returns:** `nil`
