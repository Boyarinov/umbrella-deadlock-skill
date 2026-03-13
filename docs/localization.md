# Localization

## GameLocalizer

### Methods

#### `GameLocalizer.Find(token)`

Returns localized string by token or returns empty string if token not found.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `token` | `string` | should be in format `#token` |

**Returns:** `string`

## Localizer

### Methods

#### `Localizer.Get(str)`

Returns localized string using current language.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `str` | `string` |  |

**Returns:** `string`

#### `Localizer.RegToken(str)`

Registers key (token) string to localizer.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `str` | `string` |  |

**Returns:** `nil`
