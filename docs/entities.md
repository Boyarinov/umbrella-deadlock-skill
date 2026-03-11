# Entities

## entity

*Extends [`raw_struct`](#raw_struct)*

Base game entity backed by a raw memory pointer.

### Methods

#### `entity:get_index()`

Returns the entity index in the entity system.

**Returns:** `integer` — Entity index.

#### `entity:get_handle()`

Returns the entity handle value.

**Returns:** `integer` — Entity handle.

#### `entity:valid()`

Returns whether the entity pointer is valid and safe to use.

**Returns:** `boolean` — True if pointer is valid.

#### `entity:is_alive()`

Returns whether the entity is alive.

**Returns:** `boolean` — True if alive.

#### `entity:is_dormant()`

Returns whether the entity is dormant (not actively networked).

**Returns:** `boolean` — True if dormant.

#### `entity:get_class_name()`

Returns the C++ class name of the entity.

**Returns:** `string` — Class name string.

#### `entity:get_name()`

Returns the entity's display name.

**Returns:** `string` — Display name.

#### `entity:get_origin()`

Returns the entity world position.
Returns nil when entity is invalid (null m_pGameSceneNode).

**Returns:** `Vector|nil` — World position, or nil if entity is invalid.

#### `entity:get_velocity()`

Returns entity local velocity (not absolute world velocity).
Returns nil when entity is invalid.

**Returns:** `Vector|nil` — Local velocity, or nil if entity is invalid.

#### `entity:get_angles()`

Returns entity rotation angles.
Has extra m_pGameSceneNode nil guard. Returns nil when entity is invalid.

**Returns:** `Angle|nil` — Rotation angles, or nil if entity is invalid.

#### `entity:get_bone_pos(bone_name)`

Returns world position of the named bone.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `bone_name` | `string` | Name of the bone to look up. |

**Returns:** `Vector|nil` — World position of the bone, or nil if bone not found.

#### `entity:get_bones()`

Returns all bone positions as a name-to-position map.
Returns an empty table (not nil) when entity is invalid.

**Returns:** `table<string, Vector>` — Map of bone name to world position.

#### `entity:get_attachment(attach_name)`

Returns world position of the named attachment point.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `attach_name` | `string` | Name of the attachment point. |

**Returns:** `Vector|nil` — World position of the attachment, or nil if not found.

#### `entity:get_max_health()`

Returns entity max health. Depends on m_pGameSceneNode being valid.

**Returns:** `integer` — Max health value.

#### `entity:get_modifier(modifier_name)`

Returns the modifier with the given name, or nil if not found.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `modifier_name` | `string` | Name of the modifier to look up. |

**Returns:** `modifier|nil` — Modifier instance, or nil if not present.

#### `entity:has_modifier(modifier_name)`

Returns whether the entity has a modifier with the given name.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `modifier_name` | `string` | Name of the modifier to check. |

**Returns:** `boolean` — True if modifier is present.

#### `entity:get_modifiers()`

Returns all active modifiers on this entity.

**Returns:** `modifier[]` — Array of active modifier instances.

#### `entity:get_modifier_value(modifier_value, def_value)`

Returns a single modifier property value, or def_value if not found.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `modifier_value` | `EModifierValue` | Modifier property enum to query. |
| `def_value` | `boolean\|number` | Fallback value when property is absent. |

**Returns:** `boolean|number` — Property value, or def_value if not found.

#### `entity:get_sum_modifier_value(modifier_value, def_value)`

Returns the sum of all modifier property values, or def_value if none.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `modifier_value` | `EModifierValue` | Modifier property enum to sum. |
| `def_value` | `boolean\|number` | Fallback value when no modifier provides this property. |

**Returns:** `boolean|number` — Summed value, or def_value if none found.

#### `entity:has_modifier_state(modifier_state)`

Returns whether any active modifier applies the given state.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `modifier_state` | `EModifierState` | Modifier state enum to check. |

**Returns:** `boolean` — True if any modifier provides the state.

#### `entity:get_vdata_class_name()`

Returns the VData class name.

**Returns:** `string` — VData class name string.

#### `entity:get_vdata()`

Returns VData as raw_struct for schema field access.

**Returns:** `raw_struct` — VData raw struct.

#### `entity:get_model_name()`

Returns the model file path.

**Returns:** `string` — Model file path string.

#### `entity:get_model_state()`

Returns CModelState as raw_struct.

**Returns:** `raw_struct` — CModelState raw struct.

#### `entity:get_skeleton_instance()`

Returns CSkeletonInstance as raw_struct.

**Returns:** `raw_struct` — CSkeletonInstance raw struct.

#### `entity:get_anims()`

Returns the currently playing animations on this entity.

**Returns:** `{sequence: integer, name: string, cycle: number}[]` — Array of active animation entries.

#### `entity:get_address()`

Returns memory address of entity. Only available in dev builds.

**Returns:** `string` — Memory address as a hex string.

#### `entity:get_particles()`

Returns all active particle systems on this entity.

**Returns:** `particle_info[]` — Array of active particle info entries.

#### `entity:has_particle(path)`

Returns whether the entity has an active particle matching the path.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `path` | `string` | Particle system path to match. |

**Returns:** `boolean` — True if a matching particle is active.

#### `entity:get_particle_position(path)`

Returns the origin of the first control point of the matching particle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `path` | `string` | Particle system path to match. |

**Returns:** `Vector|nil` — Control point origin, or nil if no matching particle found.

#### `entity:get_min_fov_to_bones(camera_pos, only_yaw?)`

Calculates minimum FOV angle from camera position to any bone on this entity.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `camera_pos` | `Vector` | Camera world position to measure from. |
| `only_yaw` *(optional)* | `boolean` | Default: `false`. Only consider yaw component. |

**Returns:** `number` — Minimum FOV angle in degrees to closest bone.

#### `entity:get_fireport_position(unk?)`

Returns the fireport (muzzle) world position of the entity.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `unk` *(optional)* | `integer` | Unknown parameter. |

**Returns:** `Vector|nil` — Fireport position, or nil if unavailable.

## particle_info

### Fields

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` |  |
| `control_points` | `{cp: integer, origin: Vector}[]` |  |

## player_pawn

*Extends [`entity`](#entity)*

Player character pawn entity. Represents the in-world pawn controlled by a player.

### Methods

#### `player_pawn:get_abilities()`

Returns all abilities on this player pawn.

**Returns:** `ability[]`

#### `player_pawn:get_ability(name)`

Returns the ability with the given VData class name, or nil if not found.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | VData class name of the ability. |

**Returns:** `ability|nil`

#### `player_pawn:get_primary_weapon()`

Returns the primary weapon ability, or nil if none is equipped.

**Returns:** `ability|nil`

#### `player_pawn:get_ability_by_slot(slot)`

Returns the ability in the given slot, or nil if the slot is empty.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `slot` | `EAbilitySlots_t` | Slot index to query. |

**Returns:** `ability|nil`

#### `player_pawn:get_starting_stat(stat)`

Returns the base starting value for the given stat type.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `stat` | `EStatsType` | Stat to query. |

**Returns:** `number`

#### `player_pawn:get_scaling_stat(stat)`

Returns the current scaling value for the given stat type.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `stat` | `EStatsType` | Stat to query. |

**Returns:** `number`

#### `player_pawn:get_tech_resist()`

Returns the current tech resistance value.

**Returns:** `number`

#### `player_pawn:is_visible()`

Returns whether this pawn is currently visible.
Optimized for enemy pawns; may be unreliable when called on ally pawns.

**Returns:** `boolean`

#### `player_pawn:simulate_movement(callback)`

Runs a tick-by-tick movement simulation, invoking the callback each tick.
Return true from the callback to continue simulation, false to stop it.
Errors thrown inside the callback silently stop simulation; no Lua error is raised.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `callback` | `fun(mv: move_data_t): boolean` | Called each tick. Return false to stop. |

#### `player_pawn:get_player_controller()`

Returns the CCitadelPlayerController entity associated with this pawn.

**Returns:** `entity`

#### `player_pawn:get_currency(currency)`

Returns the amount of the specified currency held by this player.
Returns 0 for out-of-range currency types without raising an error.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `currency` | `ECurrencyType` | Currency type to query. |

**Returns:** `integer`

#### `player_pawn:get_account_id()`

Returns the Steam3 account ID for this player.
To convert to SteamID64: `76561197960265728 + account_id`.
Returns 0 on failure.

**Returns:** `integer`

## move_data_t

Movement simulation data passed to the simulate_movement callback.

### Fields

| Name | Type | Description |
|------|------|-------------|
| `tickcount` | `integer` | Current tick of the simulation. |

### Methods

#### `move_data_t:get_origin()`

Returns the predicted origin at this simulation tick.

**Returns:** `Vector`

#### `move_data_t:get_velocity()`

Returns the predicted velocity at this simulation tick.

**Returns:** `Vector`

## ability

*Extends [`entity`](#entity)*

Game ability or weapon entity.

### Methods

#### `ability:get_cast_range()`

Returns the ability's cast range.

**Returns:** `number` — Cast range in game units.

#### `ability:get_level()`

Returns the current ability level.

**Returns:** `integer` — Current level (0-based).

#### `ability:get_cooldown()`

Returns the remaining cooldown in seconds.
Computed as (cooldown_end - game_time). Returns 0 if the ability is not on cooldown.

**Returns:** `number` — Remaining cooldown in seconds, or 0 if ready.

#### `ability:get_aoe_radius()`

Returns the area of effect radius.

**Returns:** `number` — AoE radius in game units.

#### `ability:can_be_executed()`

Returns the current execution state of the ability.

**Returns:** `execute_enum` — Execution state enum value.

#### `ability:get_imbued_abilities()`

Returns an array of subclass IDs (m_nSubclassIDs) of imbued abilities.
Returns integer IDs, not ability objects.

**Returns:** `integer[]` — Array of imbued ability subclass IDs.

#### `ability:has_imbue_for(m_nSubclassID)`

Returns whether the ability has an imbue for the given subclass ID.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `m_nSubclassID` | `integer` | Subclass ID to check. |

**Returns:** `boolean` — True if the ability has an imbue for the given subclass ID.

#### `ability:get_property(name)`

Returns a CitadelAbilityProperty_t from VData.
Property definitions are located in pak01_dir.vpk > scripts/abilities.vdata_c.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Property name as defined in VData. |

**Returns:** `raw_struct` — CitadelAbilityProperty_t struct from VData.

#### `ability:get_scaled_property(name)`

Returns the scaled (level-adjusted) value of a property, or nil if not found.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Property name as defined in VData. |

**Returns:** `number|nil` — Scaled property value, or nil if the property does not exist.

#### `ability:get_upgrade(level)`

Returns upgrade info at the given level. Level is 1-indexed.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `level` | `integer` | Upgrade level (1-indexed). |

**Returns:** `table<string, string>` — Upgrade info key-value pairs.

#### `ability:get_upgrades()`

Returns upgrade info for all levels.

**Returns:** `table<string, string>[]` — Array of upgrade info tables, one per level.

#### `ability:get_target()`

Returns the ability's current target entity.
Only works for the local player's abilities; silently returns nil for other players' abilities.

**Returns:** `entity|nil` — Target entity, or nil if no target or ability belongs to another player.

#### `ability:find_entities_in_cone(team_num, start_pos, direction, distance, cone_half_width, cone_angles, owner, los_check, include_extra2d_cone)`

Finds entities within a cone-shaped area.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `team_num` | `integer` | Team number filter. |
| `start_pos` | `Vector` | Cone origin point. |
| `direction` | `Vector` | Cone direction vector. |
| `distance` | `number` | Cone length. |
| `cone_half_width` | `number` | Half-width of the cone. |
| `cone_angles` | `Angle` | Cone orientation angles. |
| `owner` | `entity` | Owner entity (excluded from results). |
| `los_check` | `boolean` | Whether to perform line-of-sight checks. |
| `include_extra2d_cone` | `boolean` | Whether to include extra 2D cone check. |

**Returns:** `entity[]` — Entities found within the cone.

### `execute_enum`

| 0 # ready
| 2 # cooldown
| 3 # passive
| 7 # idk
| 10 # busy

| Value | Description |
|-------|-------------|
| `0` | ready |
| `2` | cooldown |
| `3` | passive |
| `7` | idk |
| `10` | busy |

## modifier

*Extends [`raw_struct`](#raw_struct)*

Game modifier (buff/debuff). Inherits schema field access from raw_struct.

### Methods

#### `modifier:get_class_name()`

Returns the C++ class name of this modifier.

**Returns:** `string`

#### `modifier:get_vdata_class_name()`

Returns the VData class name of this modifier.

**Returns:** `string`

#### `modifier:get_vdata()`

Returns VData as raw_struct for schema field access.

**Returns:** `raw_struct`

#### `modifier:get_ability()`

Returns the ability that created this modifier.

**Returns:** `ability`

#### `modifier:get_name()`

Returns the display name of this modifier.

**Returns:** `string`

### `player_pawn_class`

```lua
---@alias player_pawn_class "C_CitadelPlayerPawn"
```

### `entity_list.get_all()`

Returns all entities in the entity system.

**Returns:** `entity[]`

### `entity_list.by_class_name(class_name)`

Returns entities matching the given C++ class name.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `class_name` | `string` | C++ class name to filter by. |

**Returns:** `entity[]`

**Overloads:**

- `fun(class_name: player_pawn_class): player_pawn[]`

### `entity_list.by_index(index)`

Returns entity at the given index.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `index` | `integer` | Entity index. |

**Returns:** `entity|nil`

### `entity_list.by_handle(handle)`

Returns entity by handle value.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `handle` | `integer` | Entity handle. |

**Returns:** `entity|nil`

### `entity_list.local_pawn()`

Returns the local player's pawn.

**Returns:** `player_pawn`

### `entity_list.local_controller()`

Returns the local player's controller (CCitadelPlayerController).

**Returns:** `entity`
