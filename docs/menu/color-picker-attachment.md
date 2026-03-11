# CMenuColorPickerAttachment

## CMenuColorPickerAttachment

CMenuColorPickerAttachment metatable.

### `_CMenuColorPickerAttachment:Name()`

Returns widget's name.

**Returns:** `string`

### `_CMenuColorPickerAttachment:Parent()`

Returns widget's parent.

**Returns:** `CMenuSwitch|CMenuSliderInt|CMenuSliderFloat|CMenuMultiComboBox|CMenuLabel|CMenuInputBox|CMenuGroup|CMenuBind`

### `_CMenuColorPickerAttachment:Type()`

Returns widget type.

**Returns:** `Enum.WidgetType`

### `_CMenuColorPickerAttachment:Open()`

Opens parent tabs.

**Returns:** `nil`

### `_CMenuColorPickerAttachment:ForceLocalization(newText)`

Changes text in the widget. The path to the widget is not affected.\
May be used for dynamic text customization or recolor.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `newText` | `string` |  |

**Returns:** `nil`

### `_CMenuColorPickerAttachment:Visible(value)`

Gets or sets visible state. Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuColorPickerAttachment): boolean`

### `_CMenuColorPickerAttachment:Disabled(value)`

Gets or sets disabled state. Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuColorPickerAttachment): boolean`

### `_CMenuColorPickerAttachment:Get()`

Returns widget's value.

**Returns:** `Color`

### `_CMenuColorPickerAttachment:Set(value)`

Sets widget's value.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `Color` |  |

**Returns:** `nil`

### `_CMenuColorPickerAttachment:SetCallback(callback, forceCall?)`

Sets widget's on change callback.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `callback` | `fun(this: CMenuColorPickerAttachment):nil` | function to be called on widget change. |
| `forceCall` *(optional)* | `boolean` | Default: `false`. true if you want to call callback on widget creation. |

**Returns:** `nil`

### `_CMenuColorPickerAttachment:UnsetCallback(callback)`

Removes widget's on change callback.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `callback` | `fun(this: CMenuColorPickerAttachment):nil` | function to be removed from widget's callbacks. |

**Returns:** `nil`
