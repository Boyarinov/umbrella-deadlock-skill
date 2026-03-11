# CMenuComboBox

## CMenuComboBox

CMenuComboBox metatable.

### `_CMenuComboBox:Name()`

Returns widget's name.

**Returns:** `string`

### `_CMenuComboBox:Update(items, defaultValue?)`

Update the combo box values.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `items` | `string[]` |  |
| `defaultValue` *(optional)* | `integer` | Default: `0`. Index of default item. (starts from 0) |

**Returns:** `nil`

### `_CMenuComboBox:Parent()`

Returns widget's parent.

**Returns:** `CMenuGroup|CMenuGearAttachment`

### `_CMenuComboBox:Type()`

Returns widget type.

**Returns:** `Enum.WidgetType`

### `_CMenuComboBox:Open()`

Opens parent tabs.

**Returns:** `nil`

### `_CMenuComboBox:ForceLocalization(newText)`

Changes text in the widget. The path to the widget is not affected.\
May be used for dynamic text customization or recolor.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `newText` | `string` |  |

**Returns:** `nil`

### `_CMenuComboBox:ToolTip(newText)`

Gets or sets tooltip. Tooltip is displayed when mouse cursor is over the widget.\
Depends on the argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `newText` | `string` |  |

**Returns:** `string`

**Overloads:**

- `fun(this: CMenuComboBox):string`

### `_CMenuComboBox:Visible(value)`

Gets or sets visible state. Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuComboBox): boolean`

### `_CMenuComboBox:Disabled(value)`

Gets or sets disabled state. Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuComboBox): boolean`

### `_CMenuComboBox:Unsafe(value)`

Gets or sets unsafe state. Unsafe widgets have warning sign.\
Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuComboBox): boolean`

### `_CMenuComboBox:Get()`

Returns index of the selected item. It starts from 0.

**Returns:** `integer`

### `_CMenuComboBox:Set(value)`

Sets widget's value.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `integer` |  |

**Returns:** `nil`

### `_CMenuComboBox:List()`

Returns array of the items.

**Returns:** `string[]`

### `_CMenuComboBox:Image(imagePath, offset?)`

Sets widget's image.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `imagePath` | `string` | Path to the image. |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional image offset. |

**Returns:** `nil`

### `_CMenuComboBox:ImageHandle(imageHandle, offset?)`

Sets tab's image by already created handle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `imageHandle` | `integer` |  |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional image offset. |

**Returns:** `nil`

### `_CMenuComboBox:Icon(icon, offset?)`

Sets widget's icon.\
[Icons list](https://fontawesome.com/search?o=r&s=solid&f=classic)

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `icon` | `string` | icon unicode. |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional icon offset. |

**Returns:** `nil`

### `_CMenuComboBox:SetCallback(callback, forceCall?)`

Sets widget's on change callback.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `callback` | `fun(this: CMenuComboBox):nil` | function to be called on widget change. |
| `forceCall` *(optional)* | `boolean` | Default: `false`. true if you want to call callback on widget creation. |

**Returns:** `nil`

### `_CMenuComboBox:UnsetCallback(callback)`

Removes widget's on change callback.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `callback` | `fun(this: CMenuComboBox):nil` | function to be removed from widget's callbacks. |

**Returns:** `nil`

### `_CMenuComboBox:ColorPicker(name, color)`

Creates `CMenuColorPickerAttachment` and attaches it to the widget.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Name of the attachment. |
| `color` | `Color` | Default color. |

**Returns:** `CMenuColorPickerAttachment`

### `_CMenuComboBox:Gear(name, gearIcon?, useSmallFont?)`

Creates `CMenuGearAttachment` and attaches it to the widget.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Name of the attachment. |
| `gearIcon` *(optional)* | `string` | Default: `"\uf013"`. Gear FontAwesome icon. |
| `useSmallFont` *(optional)* | `boolean` | Default: `true`. Use small font for gear icon. |

**Returns:** `CMenuGearAttachment`
