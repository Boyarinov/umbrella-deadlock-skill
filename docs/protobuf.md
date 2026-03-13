# Protobuf

Google Protobuf encoding/decoding. Used for game network messages.

## protobuf_binary

Result of encoding operations.

### Fields

| Name | Type | Description |
|------|------|-------------|
| `size` | `integer` | Serialized byte count. |
| `binary` | `lightuserdata` | Raw binary pointer. Must be freed with `protobuf.free()`. |

## protobuf

### Methods

#### `protobuf.encode(name, tbl)`

Encode a Lua table to protobuf binary.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Full message type name. |
| `tbl` | `table` | Fields matching the message schema. |

**Returns:** `protobuf_binary`

#### `protobuf.encodeFromJSON(name, json)`

Encode a JSON string to protobuf binary.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Full message type name. |
| `json` | `string` | JSON-encoded message. |

**Returns:** `protobuf_binary`

#### `protobuf.decodeToJSON(name, binary, size)`

Decode binary protobuf to JSON.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Full message type name. |
| `binary` | `lightuserdata` | Raw binary pointer. |
| `size` | `integer` | Byte count of the binary data. |

**Returns:** `string` — JSON.

#### `protobuf.decodeToJSONfromString(name, base64_str)`

Decode base64-encoded protobuf to JSON.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Full message type name. |
| `base64_str` | `string` | Base64-encoded protobuf data. |

**Returns:** `string` — JSON.

#### `protobuf.decodeToJSONfromObject(ptr)`

Convert protobuf Message userdata to JSON.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `ptr` | `lightuserdata` | Protobuf Message pointer. |

**Returns:** `string` — JSON.

#### `protobuf.free(ptr)`

Free memory allocated by an encode operation.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `ptr` | `lightuserdata` | The `binary` field from `protobuf_binary`. |

**Returns:** `boolean`
