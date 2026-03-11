# CMenuMultiComboBox

## CMenuMultiComboBox

CMenuMultiComboBox metatable.

### `_CMenuMultiComboBox:Name()`

Returns widget's name.

**Returns:** `string`

### `_CMenuMultiComboBox:Update(items, enabledItems)`

Updates the multicombo values.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `items` | `string[]` |  |
| `enabledItems` | `string[]` | table of enabled items |

**Returns:** `nil`

### `_CMenuMultiComboBox:Parent()`

Returns widget's parent.

**Returns:** `CMenuGroup|CMenuGearAttachment`

### `_CMenuMultiComboBox:Type()`

Returns widget type.

**Returns:** `Enum.WidgetType`

### `_CMenuMultiComboBox:Open()`

Opens parent tabs.

**Returns:** `nil`

### `_CMenuMultiComboBox:ForceLocalization(newText)`

Changes text in the widget. The path to the widget is not affected.\
May be used for dynamic text customization or recolor.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `newText` | `string` |  |

**Returns:** `nil`

### `_CMenuMultiComboBox:ToolTip(newText)`

Gets or sets tooltip. Tooltip is displayed when mouse cursor is over the widget.\
Depends on the argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `newText` | `string` |  |

**Returns:** `string`

**Overloads:**

- `fun(this: CMenuMultiComboBox):string`

### `_CMenuMultiComboBox:Visible(value)`

Gets or sets visible state. Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuMultiComboBox): boolean`

### `_CMenuMultiComboBox:Disabled(value)`

Gets or sets disabled state. Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuMultiComboBox): boolean`

### `_CMenuMultiComboBox:Unsafe(value)`

Gets or sets unsafe state. Unsafe widgets have warning sign.\
Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuMultiComboBox): boolean`

### `_CMenuMultiComboBox:Get(itemId)`

Returns enable state of the item in combo box.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `itemId` | `string` |  |

**Returns:** `boolean`

### `_CMenuMultiComboBox:Set(enabledItems)`

Sets a new value for the item by itemId or sets a new list of enabled items

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `enabledItems` | `string[]` | A table of enabled items; other items will be disabled. |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuMultiComboBox, itemId: string, value: boolean):nil`

### `_CMenuMultiComboBox:List()`

Returns array of itemIds.

**Returns:** `string[]`

### `_CMenuMultiComboBox:ListEnabled()`

Returns array of enabled itemIds.

**Returns:** `string[]`

### `_CMenuMultiComboBox:Image(imagePath, offset?)`

Sets widget's image.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `imagePath` | `string` | Path to the image. |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional image offset. |

**Returns:** `nil`

### `_CMenuMultiComboBox:ImageHandle(imageHandle, offset?)`

Sets tab's image by already created handle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `imageHandle` | `integer` |  |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional image offset. |

**Returns:** `nil`

### `_CMenuMultiComboBox:Icon(icon, offset?)`

Sets widget's icon.\
[Icons list](https://fontawesome.com/search?o=r&s=solid&f=classic)

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `icon` | `string` | icon unicode. |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional icon offset. |

**Returns:** `nil`

### `_CMenuMultiComboBox:SetCallback(callback, forceCall?)`

Sets widget's on change callback.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `callback` | `fun(this: CMenuMultiComboBox):nil` | function to be called on widget change. |
| `forceCall` *(optional)* | `boolean` | Default: `false`. true if you want to call callback on widget creation. |

**Returns:** `nil`

### `_CMenuMultiComboBox:UnsetCallback(callback)`

Removes widget's on change callback.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `callback` | `fun(this: CMenuMultiComboBox):nil` | function to be removed from widget's callbacks. |

**Returns:** `nil`

### `_CMenuMultiComboBox:ColorPicker(name, color)`

Creates `CMenuColorPickerAttachment` and attaches it to the widget.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Name of the attachment. |
| `color` | `Color` | Default color. |

**Returns:** `CMenuColorPickerAttachment`

### `_CMenuMultiComboBox:Gear(name, gearIcon?, useSmallFont?)`

Creates `CMenuGearAttachment` and attaches it to the widget.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Name of the attachment. |
| `gearIcon` *(optional)* | `string` | Default: `"\uf013"`. Gear FontAwesome icon. |
| `useSmallFont` *(optional)* | `boolean` | Default: `true`. Use small font for gear icon. |

**Returns:** `CMenuGearAttachment`
