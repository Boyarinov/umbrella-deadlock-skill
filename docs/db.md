# Database

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
