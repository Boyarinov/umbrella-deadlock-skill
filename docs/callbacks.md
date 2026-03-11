# Callbacks

## Callbacks

Register callbacks with `:set(callback)` and unregister with `:unset(callback)`.

### `on_scripts_loaded`

Fired once when all scripts finish loading.

**Callback signature:** `fun(): nil`

### `on_pre_createmove`

Fired before CreateMove processing.

**Callback signature:** `fun(cmd: CUserCmd): nil`

### `on_createmove`

Fired during CreateMove processing.

**Callback signature:** `fun(cmd: CUserCmd): nil`

### `on_frame`

Fired every frame.

**Callback signature:** `fun(): nil`

### `on_draw`

Fired every draw frame (after on_frame).

**Callback signature:** `fun(): nil`

### `on_add_entity`

Fired when an entity is added to the entity system. Entity type is polymorphic: C_CitadelPlayerPawn -> player_pawn, C_CitadelBaseAbility -> ability, otherwise entity.

**Callback signature:** `fun(ent: entity|player_pawn|ability): nil`

### `on_late_add_entity`

Fired when an entity is added (late). Entity type is polymorphic: C_CitadelPlayerPawn -> player_pawn, C_CitadelBaseAbility -> ability, otherwise entity.

**Callback signature:** `fun(ent: entity|player_pawn|ability): nil`

### `on_remove_entity`

Fired when an entity is removed from the entity system.

**Callback signature:** `fun(ent: entity|player_pawn|ability): nil`

### `on_pre_framestage`

Fired before a frame stage change.

**Callback signature:** `fun(stage: integer): nil`

### `on_post_framestage`

Fired after a frame stage change.

**Callback signature:** `fun(stage: integer): nil`

### `on_received_net_message`

Fired when a network message is received. https://github.com/SteamDatabase/Protobufs/blob/4423890a7ade0b3e0b167ca4622d8e73c9814adf/deadlock/citadel_gameevents.proto#L5 local json = protobuf.decodeToJSONfromObject(msg)

**Callback signature:** `fun(id: integer, msg: lightuserdata): nil`

### `on_particle_create`

Particle system event. Arg table is reused across handlers in the same frame.

**Callback signature:** `fun(data: particle_create): nil`

### `on_particle_update`

Particle system event. Arg table is reused across handlers in the same frame.

**Callback signature:** `fun(data: particle_update): nil`

### `on_particle_update_transform`

Particle system event. Arg table is reused across handlers in the same frame.

**Callback signature:** `fun(data: particle_update_transform): nil`

### `on_particle_destroy`

Particle system event. Arg table is reused across handlers in the same frame.

**Callback signature:** `fun(data: particle_destroy): nil`

### `on_add_modifier`

Fired when a modifier is added to an entity.

**Callback signature:** `fun(mod: modifier, target: entity|nil, owner: entity|nil): nil`

### `on_remove_modifier`

Fired when a modifier is removed from an entity.

**Callback signature:** `fun(mod: modifier, target: entity|nil): nil`

### `on_key_event`

Fired on keyboard/mouse input. Return value is ANDed across all handlers. nil or no return is treated as true (allow key propagation).

**Callback signature:** `fun(data: key_event): boolean`

### `on_bullet_create`

Fired when a bullet is created.

**Callback signature:** `fun(data: bullet_create): nil`

---

## Callback Types

### `particle_create`

```lua
---@alias particle_create {
  entity: entity|nil,
  entity_for_modifiers: entity|nil,
  index: integer,
  name: string,
  hash: integer,
}
```

### `particle_update`

```lua
---@alias particle_update {
  entity: entity|nil,
  index: integer,
  attach_type: integer,
  attachment: integer,
  include_wearables: boolean,
  control_point: integer,
  position: Vector,
}
```

### `particle_update_transform`

```lua
---@alias particle_update_transform {
  index: integer,
  interpolation_interval: integer,
  control_point: integer,
  position: Vector,
  orientation: Angle,
}
```

### `particle_destroy`

```lua
---@alias particle_destroy {
  index: integer,
  destroy_immediately: boolean,
}
```

### `key_event`

```lua
---@alias key_event {
  key: Enum.ButtonCode,
  event: Enum.KeyEvent,
}
```

### `bullet_create`

```lua
---@alias bullet_create {
  weapon_name: string,
  shooter: entity,
  start_pos: Vector,
  direction: Vector,
  weapon: raw_struct,
}
```
