# Target Selection

## target_result

### Fields

| Name | Type | Description |
|------|------|-------------|
| `entity` | `entity` | Scored entity. |
| `score` | `number` | Computed score. |

## TargetSelection

Target selection and scoring system.

### `TargetSelection()`

Creates a new TargetSelection instance.

**Returns:** `TargetSelection`

### `_TargetSelection:add_criterion(func, weight)`

Adds a scoring criterion function.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `func` | `fun(ent: entity): number` | Scoring function. Receives entity, must return a number. Returns 0.0 on error. |
| `weight` | `number` | Weight multiplier for this criterion's score. |

### `_TargetSelection:set_filter(func)`

Sets the entity filter function. Entities that fail the filter are excluded.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `func` | `fun(ent: entity): boolean` | Filter function. Returns true to include, false to exclude. Returns false on error. |

### `_TargetSelection:set_score_threshold(v)`

Sets minimum score threshold for targets to be included.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `v` | `number` | Minimum score. |

### `_TargetSelection:set_max_targets(v)`

Sets maximum number of targets to track.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `v` | `integer` | Maximum targets. |

### `_TargetSelection:set_always_include_best(v)`

Sets whether the best-scored target is always included regardless of threshold.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `v` | `boolean` |  |

### `_TargetSelection:set_best_target_score_gap(v)`

Sets minimum score gap required for best target distinction.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `v` | `number` | Minimum score gap. |

### `_TargetSelection:update(entities)`

Evaluates targets from a Lua table of entities.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `entities` | `entity[]` | Table of entities to evaluate. |

### `_TargetSelection:update_by_class(class_name)`

Evaluates targets from the entity manager by C++ class name. Preferred over update() for performance.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `class_name` | `string` | C++ class name to query. |

### `_TargetSelection:get_targets()`

Returns scored targets sorted by score.

**Returns:** `target_result[]`

### `_TargetSelection:get_best_target()`

Returns the best-scored target entity, or nil if no targets.

**Returns:** `entity|nil`

### `_TargetSelection:set_last_shootable_target(ent)`

Sets the last shootable target. Passing a non-entity value sets nil.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `ent` | `entity\|nil` |  |

### `_TargetSelection:reset()`

Clears all scoring state, criteria, and filters.
