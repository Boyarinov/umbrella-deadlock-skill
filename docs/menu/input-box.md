# CMenuInputBox

## CMenuInputBox

CMenuInputBox metatable.

### `_CMenuInputBox:Name()`

Returns widget's name.

**Returns:** `string`

### `_CMenuInputBox:Parent()`

Returns widget's parent.

**Returns:** `CMenuGroup|CMenuGearAttachment`

### `_CMenuInputBox:Type()`

Returns widget type.

**Returns:** `Enum.WidgetType`

### `_CMenuInputBox:Open()`

Opens parent tabs.

**Returns:** `nil`

### `_CMenuInputBox:ForceLocalization(newText)`

Changes text in the widget. The path to the widget is not affected.\
May be used for dynamic text customization or recolor.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `newText` | `string` |  |

**Returns:** `nil`

### `_CMenuInputBox:ToolTip(newText)`

Gets or sets tooltip. Tooltip is displayed when mouse cursor is over the widget.\
Depends on the argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `newText` | `string` |  |

**Returns:** `string`

**Overloads:**

- `fun(this: CMenuInputBox):string`

### `_CMenuInputBox:Visible(value)`

Gets or sets visible state. Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuInputBox): boolean`

### `_CMenuInputBox:Disabled(value)`

Gets or sets disabled state. Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuInputBox): boolean`

### `_CMenuInputBox:Unsafe(value)`

Gets or sets unsafe state. Unsafe widgets have warning sign.\
Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuInputBox): boolean`

### `_CMenuInputBox:Get()`

Returns widget's value.

**Returns:** `string`

### `_CMenuInputBox:Set(value)`

Sets widget's value.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `string` |  |

**Returns:** `nil`

### `_CMenuInputBox:Image(imagePath, offset?)`

Sets widget's image.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `imagePath` | `string` | Path to the image. |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional image offset. |

**Returns:** `nil`

### `_CMenuInputBox:ImageHandle(imageHandle, offset?)`

Sets tab's image by already created handle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `imageHandle` | `integer` |  |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional image offset. |

**Returns:** `nil`

### `_CMenuInputBox:Icon(icon, offset?)`

Sets widget's icon.\
[Icons list](https://fontawesome.com/search?o=r&s=solid&f=classic)

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `icon` | `string` | icon unicode. |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional icon offset. |

**Returns:** `nil`

### `_CMenuInputBox:SetCallback(callback, forceCall?)`

Sets widget's on change callback.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `callback` | `fun(this: CMenuInputBox):nil` | function to be called on widget change. |
| `forceCall` *(optional)* | `boolean` | Default: `false`. true if you want to call callback on widget creation. |

**Returns:** `nil`

### `_CMenuInputBox:UnsetCallback(callback)`

Removes widget's on change callback.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `callback` | `fun(this: CMenuInputBox):nil` | function to be removed from widget's callbacks. |

**Returns:** `nil`

### `_CMenuInputBox:ColorPicker(name, color)`

Creates `CMenuColorPickerAttachment` and attaches it to the widget.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Name of the attachment. |
| `color` | `Color` | Default color. |

**Returns:** `CMenuColorPickerAttachment`

### `_CMenuInputBox:Gear(name, gearIcon?, useSmallFont?)`

Creates `CMenuGearAttachment` and attaches it to the widget.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Name of the attachment. |
| `gearIcon` *(optional)* | `string` | Default: `"\uf013"`. Gear FontAwesome icon. |
| `useSmallFont` *(optional)* | `boolean` | Default: `true`. Use small font for gear icon. |

**Returns:** `CMenuGearAttachment`
