# Raw Struct

## raw_struct

Base class for schema-backed game objects.
Supports field access via `__index`/`__newindex` using Source 2 schema field names.
Fields are resolved dynamically from the game's schema system at runtime.

### Indexing

- `[string]`: `any` — 
