# Tracing & Raycasting

## trace_t

Trace result object returned by ray/hull cast functions.

### Fields

| Name | Type | Description |
|------|------|-------------|
| `fraction` | `number` | How far along the ray the hit occurred. 0.0 = ray start, 1.0 = full distance traveled with no hit. |

### Methods

#### `trace_t:hit_entity()`

Returns the entity that was hit by the trace.

**Returns:** `entity` — The hit entity.

#### `trace_t:hitbox_name()`

Returns the name of the hitbox that was hit.

**Returns:** `string` — Hitbox name string, empty if no hitbox was hit.

#### `trace_t:is_visible_entity(ent, full_trace_distance)`

Returns true if the given entity is visible from the trace.
Visibility is determined by: entity is within 5 world units of the trace endpoint,
OR the trace directly hit the target entity.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `ent` | `entity` | Entity to check visibility for. |
| `full_trace_distance` | `number` | The full unobstructed distance of the ray. |

**Returns:** `boolean` — True if the entity is considered visible.

#### `trace_t:is_vertical_normal()`

Returns whether the hit surface normal is vertical (i.e. a floor or ceiling).

**Returns:** `boolean` — True if the surface normal points vertically.

## trace

Provides ray and hull casting utilities for world and entity intersection tests.

### Methods

#### `trace.line(start, end_, with, exclude, as, object_set_mask, collision_group, ignore_callback)`

Casts a ray from start to end_ and returns a trace result.
Always ignores the local player implicitly, regardless of ignore_callback.
`object_set_mask` is accepted but internally overridden to 0xF.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `start` | `Vector` | Ray start position in world space. |
| `end_` | `Vector` | Ray end position in world space. |
| `with` | `integer` | Content mask (CONTENTS flags) — which surface types to intersect. |
| `exclude` | `integer` | Content exclusion mask — surface types to skip. |
| `as` | `integer` | Solid type filter (SOLID flags). |
| `object_set_mask` | `integer` | Accepted but IGNORED — always overridden to 0xF internally. |
| `collision_group` | `integer` | Collision group filter. |
| `ignore_callback` | `fun(ent: entity): boolean` | Called per entity. Return `true` to INCLUDE the entity in trace results (name is misleading — true means keep, not skip). |

**Returns:** `trace_t` — Trace result containing fraction, hit entity, and surface info.

#### `trace.hull(start, end_, min, max, with, exclude, as, object_set_mask, collision_group, ignore_callback, ignore_local?)`

Casts a swept hull (box) from start to end_ and returns a trace result.
Unlike `trace.line`, local player is only excluded when `ignore_local` is explicitly true.
`object_set_mask` is accepted but internally overridden to 0xF.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `start` | `Vector` | Hull sweep start position in world space. |
| `end_` | `Vector` | Hull sweep end position in world space. |
| `min` | `Vector` | Hull minimum bounds (local space). |
| `max` | `Vector` | Hull maximum bounds (local space). |
| `with` | `integer` | Content mask (CONTENTS flags) — which surface types to intersect. |
| `exclude` | `integer` | Content exclusion mask — surface types to skip. |
| `as` | `integer` | Solid type filter (SOLID flags). |
| `object_set_mask` | `integer` | Accepted but IGNORED — always overridden to 0xF internally. |
| `collision_group` | `integer` | Collision group filter. |
| `ignore_callback` | `fun(ent: entity): boolean` | Called per entity. Return `true` to INCLUDE the entity in trace results. |
| `ignore_local` *(optional)* | `boolean` | When true, the local player is excluded from results. Default: false. |

**Returns:** `trace_t` — Trace result containing fraction, hit entity, and surface info.

#### `trace.bullet(start, end_, radius, ent)`

Checks whether a bullet fired from start to end_ with the given radius would hit the entity.
Uses a delta < 5 world units threshold against the trace endpoint.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `start` | `Vector` | Bullet ray start position. |
| `end_` | `Vector` | Bullet ray end position. |
| `radius` | `number` | Bullet radius used for proximity check. |
| `ent` | `entity` | Target entity to check against. |

**Returns:** `boolean` — True if the bullet trace hits or is within 5 units of the entity.

#### `trace.bullet_hitbox(start, end_, radius, ent, hitbox_name)`

Checks whether a bullet trace hits the entity AND the hitbox name matches.
Hitbox match uses substring comparison, not exact equality.
Uses a fraction >= 0.97 threshold (stricter proximity check than `trace.bullet`).

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `start` | `Vector` | Bullet ray start position. |
| `end_` | `Vector` | Bullet ray end position. |
| `radius` | `number` | Bullet radius. |
| `ent` | `entity` | Target entity to check against. |
| `hitbox_name` | `string` | Substring to match against the hit hitbox name. |

**Returns:** `boolean` — True if the trace hits the entity and the hitbox name contains hitbox_name.

#### `trace.bullet_hitbox_name(start, end_, radius, ent)`

Returns the name of the hitbox struck by the bullet trace against the given entity.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `start` | `Vector` | Bullet ray start position. |
| `end_` | `Vector` | Bullet ray end position. |
| `radius` | `number` | Bullet radius. |
| `ent` | `entity` | Target entity to trace against. |

**Returns:** `string` — Name of the hitbox that was hit, or empty string if none.
