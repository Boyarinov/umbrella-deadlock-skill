# Hero Library

## HERO_LIB

Hero-specific utilities: state checks, target finding, ability/item handling, projectile prediction, movement simulation, and UI settings.

### Methods

#### `HERO_LIB.cache_get(key, producer)`

Returns a cached value for the given key, calling producer on cache miss.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `key` | `any` | Cache key. |
| `producer` | `fun(): any` | Value producer called on cache miss. |

**Returns:** `any` — Cached or freshly produced value.

#### `HERO_LIB.is_sleeped(pawn)`

Returns whether the pawn is asleep.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pawn` | `player_pawn` |  |

**Returns:** `boolean`

#### `HERO_LIB.is_stunned(pawn)`

Returns whether the pawn is stunned.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pawn` | `player_pawn` |  |

**Returns:** `boolean`

#### `HERO_LIB.is_invulnerable(pawn)`

Returns whether the pawn is invulnerable.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pawn` | `player_pawn` |  |

**Returns:** `boolean`

#### `HERO_LIB.is_unstoppable(pawn)`

Returns whether the pawn is unstoppable.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pawn` | `player_pawn` |  |

**Returns:** `boolean`

#### `HERO_LIB.is_silenced(pawn)`

Returns whether the pawn is silenced.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pawn` | `player_pawn` |  |

**Returns:** `boolean`

#### `HERO_LIB.is_ziplining(pawn)`

Returns whether the pawn is ziplining.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pawn` | `player_pawn` |  |

**Returns:** `boolean`

#### `HERO_LIB.is_climbing_rope(pawn)`

Returns whether the pawn is climbing a rope.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pawn` | `player_pawn` |  |

**Returns:** `boolean`

#### `HERO_LIB.is_combat_abilities_disabled(pawn)`

Returns whether the pawn has combat abilities disabled.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pawn` | `player_pawn` |  |

**Returns:** `boolean`

#### `HERO_LIB.is_command_restricted(pawn)`

Returns whether the pawn is command restricted.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pawn` | `player_pawn` |  |

**Returns:** `boolean`

#### `HERO_LIB.is_out_of_game(pawn)`

Returns whether the pawn is out of game.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pawn` | `player_pawn` |  |

**Returns:** `boolean`

#### `HERO_LIB.is_ground_dashing(pawn)`

Returns whether the pawn is ground dashing.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pawn` | `player_pawn` |  |

**Returns:** `boolean`

#### `HERO_LIB.is_air_dashing(pawn)`

Returns whether the pawn is air dashing.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pawn` | `player_pawn` |  |

**Returns:** `boolean`

#### `HERO_LIB.is_any_dashing(pawn)`

Returns whether the pawn is dashing (ground or air).

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pawn` | `player_pawn` |  |

**Returns:** `boolean`

#### `HERO_LIB.is_untargetable(pawn)`

Returns whether the pawn is untargetable.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pawn` | `player_pawn` |  |

**Returns:** `boolean`

#### `HERO_LIB.is_using_blood_tribute(pawn)`

Returns whether the pawn is using Blood Tribute.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pawn` | `player_pawn` |  |

**Returns:** `boolean`

#### `HERO_LIB.is_immune_to_stun(pawn)`

Returns whether the pawn is immune to stun.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pawn` | `player_pawn` |  |

**Returns:** `boolean`

#### `HERO_LIB.is_on_ground(ent)`

Returns whether the entity is on the ground.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `ent` | `entity` |  |

**Returns:** `boolean`

#### `HERO_LIB.is_in_ivy_stone_form(pawn)`

Returns whether the pawn is in Ivy stone form.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pawn` | `player_pawn` |  |

**Returns:** `boolean`

#### `HERO_LIB.is_in_viscous_cube(pawn)`

Returns whether the pawn is inside Viscous cube.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pawn` | `player_pawn` |  |

**Returns:** `boolean`

#### `HERO_LIB.is_in_mirage_tornado(pawn)`

Returns whether the pawn is in Mirage tornado.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pawn` | `player_pawn` |  |

**Returns:** `boolean`

#### `HERO_LIB.is_casting_haze_ult(pawn)`

Returns whether the pawn is casting Haze ultimate.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pawn` | `player_pawn` |  |

**Returns:** `boolean`

#### `HERO_LIB.is_casting_krill_ult(pawn)`

Returns whether the pawn is casting Krill ultimate.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pawn` | `player_pawn` |  |

**Returns:** `boolean`

#### `HERO_LIB.is_casting_seven_ult(pawn)`

Returns whether the pawn is casting Seven ultimate.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pawn` | `player_pawn` |  |

**Returns:** `boolean`

#### `HERO_LIB.is_casting_kelvin_third(pawn)`

Returns whether the pawn is casting Kelvin third ability.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pawn` | `player_pawn` |  |

**Returns:** `boolean`

#### `HERO_LIB.is_in_ethereal_shift(pawn)`

Returns whether the pawn is in Ethereal Shift.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pawn` | `player_pawn` |  |

**Returns:** `boolean`

#### `HERO_LIB.is_ivy_stone_form(pawn)`

Returns whether the pawn is in Ivy stone form (alias).

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pawn` | `player_pawn` |  |

**Returns:** `boolean`

#### `HERO_LIB.get_health(ent)`

Returns the entity's current health.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `ent` | `entity` |  |

**Returns:** `integer|nil`

#### `HERO_LIB.get_max_health(ent)`

Returns the entity's maximum health.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `ent` | `entity` |  |

**Returns:** `integer|nil`

#### `HERO_LIB.get_health_percent(ent)`

Returns the entity's health as a fraction (0..1).

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `ent` | `entity` |  |

**Returns:** `number|nil`

#### `HERO_LIB.get_stamina(ent)`

Returns the entity's current stamina.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `ent` | `entity` |  |

**Returns:** `number`

#### `HERO_LIB.get_max_stamina(ent)`

Returns the entity's maximum stamina.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `ent` | `entity` |  |

**Returns:** `number`

#### `HERO_LIB.get_hero_id(ent)`

Returns the entity's hero ID.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `ent` | `entity` |  |

**Returns:** `integer`

#### `HERO_LIB.get_clip_size(lp, tech_power?)`

Returns current clip count and max clip size.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `lp` | `player_pawn` | Local pawn. |
| `tech_power` *(optional)* | `number` | Optional tech power override. |

**Returns:** `integer` — Current clip count., `integer` — Max clip size.

#### `HERO_LIB.has_any_particle(ent, particles)`

Returns whether the entity has any of the specified particles.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `ent` | `entity` |  |
| `particles` | `string[]` | Particle names to check. |

**Returns:** `boolean`

#### `HERO_LIB.is_ability_ready(ability, allow_casting?, additional_allowed_states?)`

Returns whether the ability is ready to use.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `ability` | `ability` |  |
| `allow_casting` *(optional)* | `boolean` | Allow if currently casting. |
| `additional_allowed_states` *(optional)* | `integer[]` | Additional allowed ability states. |

**Returns:** `boolean`

#### `HERO_LIB.is_ability_in_cd(ability, force_chargeable?)`

Returns whether the ability is on cooldown.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `ability` | `ability` |  |
| `force_chargeable` *(optional)* | `boolean` | Force chargeable cooldown check. |

**Returns:** `boolean|nil`

#### `HERO_LIB.is_ability_in_cast_delay(ability, no_start_offset?, custom_cast_delay?, custom_cast_delay_start_time?)`

Returns whether the ability is in its cast delay window.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `ability` | `ability` |  |
| `no_start_offset` *(optional)* | `boolean` | Skip start offset. |
| `custom_cast_delay` *(optional)* | `number` | Custom cast delay duration. |
| `custom_cast_delay_start_time` *(optional)* | `number` | Custom cast delay start time. |

**Returns:** `boolean|nil`

#### `HERO_LIB.is_ability_selected(lp, ability)`

Returns whether the ability is currently selected by the local pawn.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `lp` | `player_pawn` | Local pawn. |
| `ability` | `ability` |  |

**Returns:** `boolean`

#### `HERO_LIB.is_ability_in_self_cast_delay(ability)`

Returns whether the ability is in self cast delay.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `ability` | `ability` |  |

**Returns:** `boolean`

#### `HERO_LIB.get_ability_self_cast_delay(ability)`

Returns the ability's self cast delay duration.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `ability` | `ability` |  |

**Returns:** `number`

#### `HERO_LIB.is_channeling_ability(ability)`

Returns whether the ability is currently being channeled.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `ability` | `ability` |  |

**Returns:** `boolean`

#### `HERO_LIB.is_channeling_any_ability(lp, exceptions?)`

Returns whether the pawn is channeling any ability.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `lp` | `player_pawn` | Local pawn. |
| `exceptions` *(optional)* | `string[]` | Ability names to exclude from the check. |

**Returns:** `boolean`

#### `HERO_LIB.is_channeling_specific_abilities(lp, ability_names)`

Returns whether the pawn is channeling any of the specified abilities.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `lp` | `player_pawn` | Local pawn. |
| `ability_names` | `string[]` | Ability names to check. |

**Returns:** `boolean`

#### `HERO_LIB.is_in_cast_delay_specific_abilities(lp, ability_names)`

Returns whether the pawn is in cast delay for any of the specified abilities.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `lp` | `player_pawn` | Local pawn. |
| `ability_names` | `string[]` | Ability names to check. |

**Returns:** `boolean`

#### `HERO_LIB.cast_ability(cmd, lp, ability, with_alt?, with_attack?, custom_ability_slot?)`

Casts an ability using the given command.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `cmd` | `CUserCmd` | User command. |
| `lp` | `player_pawn` | Local pawn. |
| `ability` | `ability` | Ability to cast. |
| `with_alt` *(optional)* | `boolean` | Use alternate cast. |
| `with_attack` *(optional)* | `boolean` | Include attack input. |
| `custom_ability_slot` *(optional)* | `EAbilitySlots_t` | Custom ability slot override. |

#### `HERO_LIB.block_item(cmd, item)`

Blocks an item from being used this tick.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `cmd` | `CUserCmd` | User command. |
| `item` | `ability` | Item to block. |

#### `HERO_LIB.get_ability_input_mask(ability)`

Returns the input bit mask for the given ability.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `ability` | `ability` |  |

**Returns:** `InputBitMask_t|nil`

#### `HERO_LIB.get_ability_icon(ability, custom_ability_name?)`

Returns the icon path for the given ability.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `ability` | `ability` |  |
| `custom_ability_name` *(optional)* | `string` | Custom ability name override. |

**Returns:** `string|nil`

#### `HERO_LIB.get_actual_prop_value(ability, prop_name)`

Returns the actual property value for the given ability prop.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `ability` | `ability` |  |
| `prop_name` | `string` | Property name. |

**Returns:** `number`

#### `HERO_LIB.get_cached_property_num(ability, prop_name)`

Returns a cached numeric property value for the given ability prop.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `ability` | `ability` |  |
| `prop_name` | `string` | Property name. |

**Returns:** `number|nil`

#### `HERO_LIB.get_cached_property_values(ability, prop_name)`

Returns cached property values table for the given ability prop.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `ability` | `ability` |  |
| `prop_name` | `string` | Property name. |

**Returns:** `table|nil`

#### `HERO_LIB.get_cached_upgrades_num(ability)`

Returns cached upgrade numbers for the given ability.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `ability` | `ability` |  |

**Returns:** `table|nil`

#### `HERO_LIB.get_cast_delay_fraction(ability)`

Returns the cast delay fraction (0..1) for the ability.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `ability` | `ability` |  |

**Returns:** `number`

#### `HERO_LIB.get_burst_qsr_chargeup_frac(ability)`

Returns the burst QSR charge-up fraction for the ability.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `ability` | `ability` |  |

**Returns:** `number`

#### `HERO_LIB.has_ability(pawn, ability_name)`

Returns whether the pawn has the named ability.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pawn` | `player_pawn` |  |
| `ability_name` | `string` | Ability name to check. |

**Returns:** `boolean`

#### `HERO_LIB.can_be_lasthitted(pawn, allow_victor_ult?)`

Returns whether the pawn can be last-hit killed.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pawn` | `player_pawn` |  |
| `allow_victor_ult` *(optional)* | `boolean` | Allow during Victor ultimate. |

**Returns:** `boolean`

#### `HERO_LIB.handle_spirit_resist(ent, base_value)`

Applies spirit resistance to a base damage value.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `ent` | `entity` | Target entity. |
| `base_value` | `number` | Raw spirit damage. |

**Returns:** `number` — Damage after spirit resistance.

#### `HERO_LIB.get_qsr_damage(lp, target, ability, damage)`

Calculates QSR (Quick Silver Reload) bonus damage.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `lp` | `player_pawn` | Local pawn. |
| `target` | `player_pawn` | Target pawn. |
| `ability` | `ability` | Ability used. |
| `damage` | `number` | Base damage. |

**Returns:** `number` — Adjusted damage.

#### `HERO_LIB.get_mystic_burst_damage(lp, target, damage_no_resist)`

Calculates mystic burst bonus damage after resistance.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `lp` | `player_pawn` | Local pawn. |
| `target` | `player_pawn` | Target pawn. |
| `damage_no_resist` | `number` | Damage before resistance. |

**Returns:** `number` — Damage after mystic burst calculation.

#### `HERO_LIB.handle_spellbreaker_reduction(target, damage)`

Applies Spellbreaker damage reduction to the given damage.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `target` | `player_pawn` | Target pawn. |
| `damage` | `number` | Incoming damage. |

**Returns:** `number` — Damage after Spellbreaker reduction.

#### `HERO_LIB.find_target(cmd, lp, is_combo)`

Finds the best target for the current context.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `cmd` | `CUserCmd` | User command. |
| `lp` | `player_pawn` | Local pawn. |
| `is_combo` | `boolean` | Whether this is a combo target search. |

**Returns:** `player_pawn|nil`

#### `HERO_LIB.find_combo_target(cmd, lp)`

Finds the best combo target.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `cmd` | `CUserCmd` | User command. |
| `lp` | `player_pawn` | Local pawn. |

**Returns:** `player_pawn|nil`

#### `HERO_LIB.find_helper_target(cmd, lp)`

Finds the best helper target.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `cmd` | `CUserCmd` | User command. |
| `lp` | `player_pawn` | Local pawn. |

**Returns:** `player_pawn|nil`

#### `HERO_LIB.get_nearest_enemy(lp, pos, only_visible?, with_time_predict?, time?, check_active?, additional_filter_func?)`

Returns the nearest enemy pawn.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `lp` | `player_pawn` | Local pawn. |
| `pos` | `Vector` | Origin position. |
| `only_visible` *(optional)* | `boolean` | Only consider visible enemies. |
| `with_time_predict` *(optional)* | `boolean` | Use time-based prediction. |
| `time` *(optional)* | `number` | Prediction time. |
| `check_active` *(optional)* | `boolean` | Only consider active enemies. |
| `additional_filter_func` *(optional)* | `fun(pawn: player_pawn): boolean` | Extra filter. |

**Returns:** `player_pawn|nil`

#### `HERO_LIB.get_all_heroes(lp, allow_lp?, allow_allies?, allow_enemies?, only_alive?)`

Returns all hero pawns matching the given filters.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `lp` | `player_pawn` | Local pawn. |
| `allow_lp` *(optional)* | `boolean` | Include local pawn. |
| `allow_allies` *(optional)* | `boolean` | Include allies. |
| `allow_enemies` *(optional)* | `boolean` | Include enemies. |
| `only_alive` *(optional)* | `boolean` | Only alive heroes. |

**Returns:** `player_pawn[]`

#### `HERO_LIB.get_all_heroes_with_ability(ability_name, lp, allow_lp?, allow_allies?, allow_enemies?, only_alive?)`

Returns all hero pawns that have the named ability.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `ability_name` | `string` | Ability name to check. |
| `lp` | `player_pawn` | Local pawn. |
| `allow_lp` *(optional)* | `boolean` | Include local pawn. |
| `allow_allies` *(optional)* | `boolean` | Include allies. |
| `allow_enemies` *(optional)* | `boolean` | Include enemies. |
| `only_alive` *(optional)* | `boolean` | Only alive heroes. |

**Returns:** `player_pawn[]` — Matching pawns., `ability[]` — Corresponding abilities.

#### `HERO_LIB.get_all_heroes_with_modifier(modifier, lp, allow_lp?, allow_allies?, allow_enemies?, only_alive?)`

Returns all hero pawns that have the given modifier.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `modifier` | `modifier` | Modifier to check. |
| `lp` | `player_pawn` | Local pawn. |
| `allow_lp` *(optional)* | `boolean` | Include local pawn. |
| `allow_allies` *(optional)* | `boolean` | Include allies. |
| `allow_enemies` *(optional)* | `boolean` | Include enemies. |
| `only_alive` *(optional)* | `boolean` | Only alive heroes. |

**Returns:** `player_pawn[]`

#### `HERO_LIB.get_all_heroes_with_modifier_state(modifier_state, lp, allow_lp?, allow_allies?, allow_enemies?, only_alive?)`

Returns all hero pawns that have the given modifier state.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `modifier_state` | `EModifierState` | Modifier state to check. |
| `lp` | `player_pawn` | Local pawn. |
| `allow_lp` *(optional)* | `boolean` | Include local pawn. |
| `allow_allies` *(optional)* | `boolean` | Include allies. |
| `allow_enemies` *(optional)* | `boolean` | Include enemies. |
| `only_alive` *(optional)* | `boolean` | Only alive heroes. |

**Returns:** `player_pawn[]`

#### `HERO_LIB.get_heroes_in_radius(lp, pos, radius, allow_allies?, allow_enemies?, only_visible?, check_active?, with_time_predict?, time?)`

Returns all hero pawns within the given radius.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `lp` | `player_pawn` | Local pawn. |
| `pos` | `Vector` | Center position. |
| `radius` | `number` | Search radius. |
| `allow_allies` *(optional)* | `boolean` | Include allies. |
| `allow_enemies` *(optional)* | `boolean` | Include enemies. |
| `only_visible` *(optional)* | `boolean` | Only visible pawns. |
| `check_active` *(optional)* | `boolean` | Only active pawns. |
| `with_time_predict` *(optional)* | `boolean` | Use time-based prediction. |
| `time` *(optional)* | `number` | Prediction time. |

**Returns:** `player_pawn[]`

#### `HERO_LIB.get_fov_to_entity(camera_pos, target, only_yaw?, cmd?)`

Returns the FOV angle from camera to the target entity.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `camera_pos` | `Vector` | Camera position. |
| `target` | `player_pawn` | Target pawn. |
| `only_yaw` *(optional)* | `boolean` | Only consider yaw angle. |
| `cmd` *(optional)* | `CUserCmd` | User command for view angles. |

**Returns:** `number` — FOV angle in degrees.

#### `HERO_LIB.is_target_within_fov(camera_pos, target, fov, only_yaw?, cmd?)`

Returns whether the target is within the given FOV.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `camera_pos` | `Vector` | Camera position. |
| `target` | `player_pawn` | Target pawn. |
| `fov` | `number` | Maximum FOV angle. |
| `only_yaw` *(optional)* | `boolean` | Only consider yaw angle. |
| `cmd` *(optional)* | `CUserCmd` | User command for view angles. |

**Returns:** `boolean`

#### `HERO_LIB.get_fov_to_pos(camera_pos, pos, custom_camera_angles?, only_yaw?, cmd?)`

Returns the FOV angle from camera to a world position.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `camera_pos` | `Vector` | Camera position. |
| `pos` | `Vector` | World position. |
| `custom_camera_angles` *(optional)* | `Angle` | Custom camera angles override. |
| `only_yaw` *(optional)* | `boolean` | Only consider yaw angle. |
| `cmd` *(optional)* | `CUserCmd` | User command for view angles. |

**Returns:** `number` — FOV angle in degrees.

#### `HERO_LIB.is_pos_within_fov(camera_pos, pos, fov, custom_camera_angles?, only_yaw?, cmd?)`

Returns whether a world position is within the given FOV.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `camera_pos` | `Vector` | Camera position. |
| `pos` | `Vector` | World position. |
| `fov` | `number` | Maximum FOV angle. |
| `custom_camera_angles` *(optional)* | `Angle` | Custom camera angles override. |
| `only_yaw` *(optional)* | `boolean` | Only consider yaw angle. |
| `cmd` *(optional)* | `CUserCmd` | User command for view angles. |

**Returns:** `boolean`

#### `HERO_LIB.get_fov_to_bones(bones, custom_camera_pos?)`

Returns the minimum FOV angle across the given bone positions.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `bones` | `table<string, Vector>` | Bone name to position map. |
| `custom_camera_pos` *(optional)* | `Vector` | Custom camera position. |

**Returns:** `number|nil`

#### `HERO_LIB.get_closest_bone_pos(target, custom_camera_pos?)`

Returns the closest bone position on the target to the camera.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `target` | `player_pawn` | Target pawn. |
| `custom_camera_pos` *(optional)* | `Vector` | Custom camera position. |

**Returns:** `Vector|nil`

#### `HERO_LIB.get_bone_positions(target, ignore_legs?)`

Returns a map of bone names to world positions for the target.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `target` | `player_pawn` | Target pawn. |
| `ignore_legs` *(optional)* | `boolean` | Exclude leg bones. |

**Returns:** `table<string, Vector>`

#### `HERO_LIB.get_target_pos(target)`

Returns the predicted target position used for aiming.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `target` | `player_pawn` | Target pawn. |

**Returns:** `Vector|nil`

#### `HERO_LIB.no_obs_to_target(target, custom_camera_pos?, custom_lp?, custom_allowed_fraction?)`

Returns whether there is no obstruction between the camera and the target.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `target` | `player_pawn` | Target pawn. |
| `custom_camera_pos` *(optional)* | `Vector` | Custom camera position. |
| `custom_lp` *(optional)* | `player_pawn` | Custom local pawn for trace filtering. |
| `custom_allowed_fraction` *(optional)* | `number` | Maximum allowed trace fraction. |

**Returns:** `boolean`

#### `HERO_LIB.no_obs_to_pos(pos, custom_camera_pos?, custom_lp?, target?, custom_allowed_fraction?)`

Returns whether there is no obstruction between the camera and a position.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pos` | `Vector` | World position. |
| `custom_camera_pos` *(optional)* | `Vector` | Custom camera position. |
| `custom_lp` *(optional)* | `player_pawn` | Custom local pawn for trace filtering. |
| `target` *(optional)* | `player_pawn` | Target pawn to ignore in trace. |
| `custom_allowed_fraction` *(optional)* | `number` | Maximum allowed trace fraction. |

**Returns:** `boolean`

#### `HERO_LIB.is_line_free(start_pos, end_pos, lp, target?, allowed_fraction?)`

Returns whether the line between two positions is free of obstructions.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `start_pos` | `Vector` | Start position. |
| `end_pos` | `Vector` | End position. |
| `lp` | `player_pawn` | Local pawn for trace filtering. |
| `target` *(optional)* | `player_pawn` | Target pawn to ignore in trace. |
| `allowed_fraction` *(optional)* | `number` | Maximum allowed trace fraction. |

**Returns:** `boolean` — Whether the line is free., `number` — Trace fraction.

#### `HERO_LIB.is_target_within_cone(lp, cmd, target_position, ability, angle_scale?, from_lp_origin?, with_pitch?, use_half_width_method?)`

Returns whether the target position is within the ability cone.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `lp` | `player_pawn` | Local pawn. |
| `cmd` | `CUserCmd` | User command. |
| `target_position` | `Vector` | Target position to check. |
| `ability` | `ability` | Ability with cone properties. |
| `angle_scale` *(optional)* | `number` | Scale factor for cone angle. |
| `from_lp_origin` *(optional)* | `boolean` | Measure from pawn origin instead of camera. |
| `with_pitch` *(optional)* | `boolean` | Include pitch in cone check. |
| `use_half_width_method` *(optional)* | `boolean` | Use half-width cone method. |

**Returns:** `boolean` — Whether inside the cone., `number` — Angle to the target.

#### `HERO_LIB.is_within_wave_width(camera_pos, camera_forward, target_pos, wave_width)`

Returns whether the target position is within the wave width.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `camera_pos` | `Vector` | Camera position. |
| `camera_forward` | `Vector` | Camera forward direction. |
| `target_pos` | `Vector` | Target position. |
| `wave_width` | `number` | Wave width. |

**Returns:** `boolean`

#### `HERO_LIB.is_already_aiming(predicted_pos, cmd, threshold?)`

Returns whether the crosshair is already aimed at the predicted position.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `predicted_pos` | `Vector` | Predicted target position. |
| `cmd` | `CUserCmd` | User command. |
| `threshold` *(optional)* | `number` | FOV threshold in degrees. |

**Returns:** `boolean`

#### `HERO_LIB.hull_projectile_will_hit(local_pawn, camera_pos, target_pos, target, abil, ignore_team?, custom_radius?)`

Returns whether a hull projectile will hit the target.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `local_pawn` | `player_pawn` | Local pawn. |
| `camera_pos` | `Vector` | Camera position. |
| `target_pos` | `Vector` | Target position. |
| `target` | `player_pawn` | Target pawn. |
| `abil` | `ability` | Ability with projectile properties. |
| `ignore_team` *(optional)* | `boolean` | Ignore team check. |
| `custom_radius` *(optional)* | `number` | Custom hull radius. |

**Returns:** `boolean`

#### `HERO_LIB.predict_projectile(info_from, cast_point, target_pos, target_velocity, ability, ignore_z?, custom_proj_speed?)`

Predicts projectile landing position using linear extrapolation.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `info_from` | `HERO_LIB.ENUM_PPS_INFO_FROM` | Source of projectile info. |
| `cast_point` | `Vector` | Projectile origin. |
| `target_pos` | `Vector` | Target position. |
| `target_velocity` | `Vector` | Target velocity. |
| `ability` | `ability` | Ability with projectile properties. |
| `ignore_z` *(optional)* | `boolean` | Ignore Z axis in prediction. |
| `custom_proj_speed` *(optional)* | `number` | Custom projectile speed. |

**Returns:** `Vector` — Predicted aim position., `Vector` — Predicted target position at impact., `number` — Predicted time of flight.

#### `HERO_LIB.predict_projectile_simulated(need_debug, info_from, sim_type, aim_to_pos, target, ability, custom_lp?, custom_proj_speed?, custom_max_range?)`

Predicts projectile landing position using movement simulation.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `need_debug` | `boolean` | Enable debug visualization. |
| `info_from` | `HERO_LIB.ENUM_PPS_INFO_FROM` | Source of projectile info. |
| `sim_type` | `HERO_LIB.ENUM_MV_SIM_TYPE` | Movement simulation type. |
| `aim_to_pos` | `HERO_LIB.ENUM_PPS_AIM_TO_POS` | Aim position type. |
| `target` | `player_pawn` | Target pawn. |
| `ability` | `ability` | Ability with projectile properties. |
| `custom_lp` *(optional)* | `player_pawn` | Custom local pawn. |
| `custom_proj_speed` *(optional)* | `number` | Custom projectile speed. |
| `custom_max_range` *(optional)* | `number` | Custom maximum range. |

**Returns:** `Vector|nil` — Predicted aim position., `Vector|nil` — Predicted target position at impact., `Vector[]` — Simulated projectile path points., `Vector[]` — Simulated target path points.

#### `HERO_LIB.simulate_pawn_movement(pawn, sim_type, callback)`

Simulates pawn movement using the given simulation type.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pawn` | `player_pawn` | Pawn to simulate. |
| `sim_type` | `HERO_LIB.ENUM_MV_SIM_TYPE` | Simulation type. |
| `callback` | `fun(pos: Vector, vel: Vector, step: integer): boolean` | Step callback, return false to stop. |

**Returns:** `boolean` — Whether simulation completed.

#### `HERO_LIB.simulate_movement_for_duration(target, duration, additional_movement_slow?)`

Simulates pawn movement for a given duration and returns path points.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `target` | `player_pawn` | Target pawn. |
| `duration` | `number` | Simulation duration in seconds. |
| `additional_movement_slow` *(optional)* | `number` | Additional movement slow factor. |

**Returns:** `Vector[]` — Simulated path points., `Vector` — Final predicted position.

#### `HERO_LIB.rotate_movement(cmd, lp, only_yaw, need_angle?, need_dir?, need_pos?, block_movement?, move_on?, move_from?)`

Rotates movement input to face a target direction or position.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `cmd` | `CUserCmd` | User command. |
| `lp` | `player_pawn` | Local pawn. |
| `only_yaw` | `boolean` | Only rotate yaw. |
| `need_angle` *(optional)* | `Angle` | Target angle. |
| `need_dir` *(optional)* | `Vector` | Target direction. |
| `need_pos` *(optional)* | `Vector` | Target position. |
| `block_movement` *(optional)* | `boolean` | Block movement input. |
| `move_on` *(optional)* | `Vector` | Position to move toward. |
| `move_from` *(optional)* | `Vector` | Position to move away from. |

**Returns:** `boolean` — Whether rotation was applied.

#### `HERO_LIB.aim_psilent_default(cmd, smooth, pos, target, radius, allow_psilent, allowed_min_fov, on_aimed_callback?, on_process_callback?, angle?)`

Performs psilent aiming with smooth interpolation.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `cmd` | `CUserCmd` | User command. |
| `smooth` | `number` | Smooth factor. |
| `pos` | `Vector` | Target position. |
| `target` | `player_pawn` | Target pawn. |
| `radius` | `number` | Aim radius. |
| `allow_psilent` | `boolean` | Allow psilent aiming. |
| `allowed_min_fov` | `number` | Minimum FOV for psilent. |
| `on_aimed_callback` *(optional)* | `fun()` | Called when aim is on target. |
| `on_process_callback` *(optional)* | `fun()` | Called each processing step. |
| `angle` *(optional)* | `Angle` | Custom aim angle. |

#### `HERO_LIB.handle_target_items(cmd, lp, target, items_multiselect, smooth, allow_psilent)`

Handles casting targeted items on the given target.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `cmd` | `CUserCmd` | User command. |
| `lp` | `player_pawn` | Local pawn. |
| `target` | `player_pawn` | Target pawn. |
| `items_multiselect` | `table` | Items multiselect widget value. |
| `smooth` | `number` | Aim smooth factor. |
| `allow_psilent` | `boolean` | Allow psilent aiming. |

**Returns:** `boolean` — Whether an item was used.

#### `HERO_LIB.handle_aoe_items(cmd, lp, target, items_multiselect)`

Handles casting AOE items at the target's position.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `cmd` | `CUserCmd` | User command. |
| `lp` | `player_pawn` | Local pawn. |
| `target` | `player_pawn` | Target pawn. |
| `items_multiselect` | `table` | Items multiselect widget value. |

**Returns:** `boolean` — Whether an item was used.

#### `HERO_LIB.handle_non_target_items(cmd, lp, target, items_multiselect)`

Handles casting non-targeted items near the target.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `cmd` | `CUserCmd` | User command. |
| `lp` | `player_pawn` | Local pawn. |
| `target` | `player_pawn` | Target pawn. |
| `items_multiselect` | `table` | Items multiselect widget value. |

**Returns:** `boolean` — Whether an item was used.

#### `HERO_LIB.handle_all_items(cmd, me, target, items_enabled, items_smooth, items_psilent, aoe_widget, target_widget, non_target_widget)`

Handles all item categories for the target.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `cmd` | `CUserCmd` | User command. |
| `me` | `player_pawn` | Local pawn. |
| `target` | `player_pawn` | Target pawn. |
| `items_enabled` | `boolean` | Whether items are enabled. |
| `items_smooth` | `number` | Aim smooth factor. |
| `items_psilent` | `boolean` | Allow psilent aiming. |
| `aoe_widget` | `table` | AOE items widget value. |
| `target_widget` | `table` | Target items widget value. |
| `non_target_widget` | `table` | Non-target items widget value. |

**Returns:** `boolean` — Whether an item was used.

#### `HERO_LIB.create_item_multiselects(parent)`

Creates item multiselect UI widgets under the given parent.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `parent` | `table` | UI parent element. |

**Returns:** `ui_lib_element_gear` — Weapon items widget., `ui_lib_element_gear` — Vitality items widget., `ui_lib_element_gear` — Spirit items widget., `ui_lib_element_gear` — AOE items widget., `ui_lib_element_gear` — Target items widget., `ui_lib_element_gear` — Non-target items widget.

#### `HERO_LIB.use_blood_tribute(cmd, lp, blood_tribute, value)`

Uses Blood Tribute active item.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `cmd` | `CUserCmd` | User command. |
| `lp` | `player_pawn` | Local pawn. |
| `blood_tribute` | `ability` | Blood Tribute item. |
| `value` | `number` | Health threshold value. |

#### `HERO_LIB.is_same_team(pawn1, pawn2)`

Returns whether two pawns are on the same team.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pawn1` | `player_pawn` | First pawn. |
| `pawn2` | `player_pawn` | Second pawn. |

**Returns:** `boolean`

#### `HERO_LIB.is_using_free_cursor(cmd)`

Returns whether the player is using the free cursor.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `cmd` | `CUserCmd` | User command. |

**Returns:** `boolean`

#### `HERO_LIB.can_combo(lp, cmd, allow_cursor?)`

Returns whether a combo can be executed.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `lp` | `player_pawn` | Local pawn. |
| `cmd` | `CUserCmd` | User command. |
| `allow_cursor` *(optional)* | `boolean` | Allow during free cursor. |

**Returns:** `boolean`

#### `HERO_LIB.closest_point_on_line(start_point, end_point, point)`

Returns the closest point on a line segment to a given point.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `start_point` | `Vector` | Line start. |
| `end_point` | `Vector` | Line end. |
| `point` | `Vector` | Query point. |

**Returns:** `Vector` — Closest point on the line.

#### `HERO_LIB.apply_item_schema(widget, items)`

Applies item schema configuration to a widget.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `widget` | `table` | UI widget. |
| `items` | `table` | Item configuration. |

#### `HERO_LIB.get_item_ui_element(item, value)`

Returns a UI element table for the given item and value.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `item` | `table` | Item data. |
| `value` | `any` | Item value. |

**Returns:** `table` — UI element descriptor.

#### `HERO_LIB.get_item_category_by_name(name)`

Returns the item category name for the given item name.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Item name. |

**Returns:** `string|nil` — Category name.

#### `HERO_LIB.get_combo_fov(lp)`

Returns the combo FOV setting.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `lp` | `player_pawn` | Local pawn. |

**Returns:** `number`

#### `HERO_LIB.get_helper_fov(lp)`

Returns the helper FOV setting.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `lp` | `player_pawn` | Local pawn. |

**Returns:** `number`

#### `HERO_LIB.get_combo_distance(lp)`

Returns the combo distance setting.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `lp` | `player_pawn` | Local pawn. |

**Returns:** `number`

#### `HERO_LIB.get_helper_distance(lp)`

Returns the helper distance setting.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `lp` | `player_pawn` | Local pawn. |

**Returns:** `number`

#### `HERO_LIB.get_combo_priority(lp)`

Returns the combo priority setting.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `lp` | `player_pawn` | Local pawn. |

**Returns:** `number`

#### `HERO_LIB.get_helper_priority(lp)`

Returns the helper priority setting.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `lp` | `player_pawn` | Local pawn. |

**Returns:** `number`

#### `HERO_LIB.get_combo_ignore(lp)`

Returns the combo ignore list.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `lp` | `player_pawn` | Local pawn. |

**Returns:** `table`

#### `HERO_LIB.get_helper_ignore(lp)`

Returns the helper ignore list.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `lp` | `player_pawn` | Local pawn. |

**Returns:** `table`

#### `HERO_LIB.get_combo_lock_target(lp)`

Returns the combo lock target setting.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `lp` | `player_pawn` | Local pawn. |

**Returns:** `number`

### `HERO_LIB.UNITS_TO_METERS`

**Type:** `number`

Conversion factor from Source 2 units to meters.

### `HERO_LIB.lp`

**Type:** `player_pawn|nil`

Cached local pawn, updated each tick.

### `HERO_LIB.lp_hero_id`

**Type:** `integer`

Cached local hero ID.

### `HERO_LIB.is_lp_valid`

**Type:** `boolean|nil`

Whether the local pawn reference is valid.

### `HERO_LIB.is_lp_alive`

**Type:** `boolean|nil`

Whether the local pawn is alive.

### `HERO_LIB.CACHE`

**Type:** `table`

Internal cache storage.

### `HERO_LIB.fix_hero_names`

**Type:** `table<string, string>`

Maps internal hero names to fixed image names.

### `HERO_LIB.all_active_items`

**Type:** `table`

All active items with name/image/category fields.

### `HERO_LIB.whitelist_bones`

**Type:** `table<string, boolean>`

Whitelisted bone names for tracing.

### `HERO_LIB.whitelist_bones_no_legs`

**Type:** `table<string, boolean>`

Whitelisted bone names excluding legs.

### `HERO_LIB.whitelist_bunny_bones`

**Type:** `table<string, boolean>`

Whitelisted bone names for bunny model.

### `HERO_LIB.whitelist_cat_bones`

**Type:** `table<string, boolean>`

Whitelisted bone names for cat model.

### `HERO_LIB.whitelist_bones_only_head_body`

**Type:** `table<string, boolean>`

Whitelisted bone names for head and body only.

### `math.clamp(value, min, max)`

Clamps a value between min and max.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `number` | Value to clamp. |
| `min` | `number` | Minimum bound. |
| `max` | `number` | Maximum bound. |

**Returns:** `number` — Clamped value.

### `ter(cond, val1, val2)`

Ternary helper: returns val1 if cond is truthy, val2 otherwise.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `cond` | `any` | Condition to evaluate. |
| `val1` | `any` | Value returned when truthy. |
| `val2` | `any` | Value returned when falsy. |

**Returns:** `any`
