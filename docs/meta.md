# Meta Tracker

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
