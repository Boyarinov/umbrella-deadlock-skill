# CMenuGearAttachment

## CMenuGearAttachment

CMenuGearAttachment metatable.

### `_CMenuGearAttachment:Name()`

Returns widget's name.

**Returns:** `string`

### `_CMenuGearAttachment:Parent()`

Returns widget's parent.

**Returns:** `CMenuSwitch|CMenuSliderInt|CMenuSliderFloat|CMenuMultiComboBox|CMenuLabel|CMenuInputBox|CMenuComboBox|CMenuBind`

### `_CMenuGearAttachment:Type()`

Returns widget type.

**Returns:** `Enum.WidgetType`

### `_CMenuGearAttachment:Open()`

Opens parent tabs.

**Returns:** `nil`

### `_CMenuGearAttachment:ForceLocalization(newText)`

Changes text in the widget. The path to the widget is not affected.\
May be used for dynamic text customization or recolor.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `newText` | `string` |  |

**Returns:** `nil`

### `_CMenuGearAttachment:Find(widgetName)`

Finds the widget by name.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `widgetName` | `string` |  |

**Returns:** `CMenuSwitch|CMenuBind|CMenuSliderFloat|CMenuSliderInt|CMenuColorPicker|CMenuComboBox|CMenuMultiComboBox|CMenuMultiSelect|CMenuInputBox|CMenuLabel|nil`

### `_CMenuGearAttachment:Switch(switchName, defaultValue?, imageIcon?)`

Creates new `CMenuSwitch`.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `switchName` | `string` |  |
| `defaultValue` *(optional)* | `boolean` | Default: `false` |
| `imageIcon` *(optional)* | `string` | Default: `""`. Path to image or FontAwesome icon unicode. |

**Returns:** `CMenuSwitch`

### `_CMenuGearAttachment:Bind(bindName, defaultValue?, imageIcon?)`

Creates new `CMenuBind`.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `bindName` | `string` |  |
| `defaultValue` *(optional)* | `Enum.ButtonCode` | Default: `Enum.ButtonCode.BUTTON_CODE_INVALID` |
| `imageIcon` *(optional)* | `string` | Default: `""`. Path to image or FontAwesome icon unicode. |

**Returns:** `CMenuBind`

### `_CMenuGearAttachment:Slider(sliderName, minValue, maxValue, defaultValue, format?)`

Creates new `CMenuSliderInt` or `CMenuSliderFloat` depents on arg types.\
`minValue`, `maxValue` and `defaultValue` should be integer to create `CMenuSliderInt`.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `sliderName` | `string` |  |
| `minValue` | `integer` |  |
| `maxValue` | `integer` |  |
| `defaultValue` | `integer` |  |
| `format` *(optional)* | `string\|fun(value: integer):string` | Default: `"%d"`. Format string or function to format value. See example. |

**Returns:** `CMenuSliderInt`

**Overloads:**

- `fun(this: CMenuGearAttachment, sliderName: string, minValue: number, maxValue: number, defaultValue: number, format: string|fun(value: number):string): CMenuSliderFloat`

### `_CMenuGearAttachment:ColorPicker(colorPickerName, color, imageIcon?)`

Creates new `CMenuColorPicker`.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `colorPickerName` | `string` |  |
| `color` | `Color` |  |
| `imageIcon` *(optional)* | `string` | Default: `""`. Path to image or FontAwesome icon unicode. |

**Returns:** `CMenuColorPicker`

### `_CMenuGearAttachment:Combo(comboName, items, defaultValue?)`

Creates new `CMenuComboBox`.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `comboName` | `string` |  |
| `items` | `string[]` |  |
| `defaultValue` *(optional)* | `integer` | Default: `0`. Index of default item. (starts from 0) |

**Returns:** `CMenuComboBox`

### `_CMenuGearAttachment:MultiCombo(multiComboName, items, enabledItems)`

Creates new `CMenuMultiComboBox`.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `multiComboName` | `string` |  |
| `items` | `string[]` |  |
| `enabledItems` | `string[]` | table of enabled items |

**Returns:** `CMenuMultiComboBox`

### `_CMenuGearAttachment:MultiSelect(multiSelectName, items, expanded?)`

Creates new `CMenuMultiSelect`.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `multiSelectName` | `string` |  |
| `items` | `{nameId: string, imagePath: string, isEnabled: boolean}[]` | See example. |
| `expanded` *(optional)* | `boolean` | Default: `false`. false if you want to create MultiSelect in collapsed state. |

**Returns:** `CMenuMultiSelect`

### `_CMenuGearAttachment:Input(inputName, defaultValue?, imageIcon?)`

Creates new `CMenuInputBox`.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `inputName` | `string` |  |
| `defaultValue` *(optional)* | `string` | Default: `""` |
| `imageIcon` *(optional)* | `string` | Default: `""`. Path to image or FontAwesome icon unicode. |

**Returns:** `CMenuInputBox`

### `_CMenuGearAttachment:Label(labelText, imageIcon?)`

Creates new `CMenuLabel`.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `labelText` | `string` |  |
| `imageIcon` *(optional)* | `string` | Default: `""`. Path to image or FontAwesome icon unicode. |

**Returns:** `CMenuLabel`

### `_CMenuGearAttachment:Visible(value)`

Gets or sets visible state. Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuGearAttachment): boolean`

### `_CMenuGearAttachment:Disabled(value)`

Gets or sets disabled state. Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuGearAttachment): boolean`
