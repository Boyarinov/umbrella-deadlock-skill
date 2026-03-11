# CMenuSliderFloat

## CMenuSliderFloat

CMenuSliderFloat metatable.

### `_CMenuSliderFloat:Update(minValue, maxValue, defaultValue)`

Updates the slider values.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `minValue` | `number` |  |
| `maxValue` | `number` |  |
| `defaultValue` | `number` |  |

**Returns:** `nil`

### `_CMenuSliderFloat:Name()`

Returns widget's name.

**Returns:** `string`

### `_CMenuSliderFloat:Parent()`

Returns widget's parent.

**Returns:** `CMenuGroup|CMenuGearAttachment`

### `_CMenuSliderFloat:Type()`

Returns widget type.

**Returns:** `Enum.WidgetType`

### `_CMenuSliderFloat:Open()`

Opens parent tabs.

**Returns:** `nil`

### `_CMenuSliderFloat:ForceLocalization(newText)`

Changes text in the widget. The path to the widget is not affected.\
May be used for dynamic text customization or recolor.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `newText` | `string` |  |

**Returns:** `nil`

### `_CMenuSliderFloat:ToolTip(newText)`

Gets or sets tooltip. Tooltip is displayed when mouse cursor is over the widget.\
Depends on the argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `newText` | `string` |  |

**Returns:** `string`

**Overloads:**

- `fun(this: CMenuSliderFloat):string`

### `_CMenuSliderFloat:Visible(value)`

Gets or sets visible state. Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuSliderFloat): boolean`

### `_CMenuSliderFloat:Disabled(value)`

Gets or sets disabled state. Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuSliderFloat): boolean`

### `_CMenuSliderFloat:Unsafe(value)`

Gets or sets unsafe state. Unsafe widgets have warning sign.\
Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuSliderFloat): boolean`

### `_CMenuSliderFloat:Get()`

Returns widget's value.

**Returns:** `number`

### `_CMenuSliderFloat:Set(value)`

Sets widget's value.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `number` |  |

**Returns:** `nil`

### `_CMenuSliderFloat:Image(imagePath, offset?)`

Sets widget's image.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `imagePath` | `string` | Path to the image. |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional image offset. |

**Returns:** `nil`

### `_CMenuSliderFloat:ImageHandle(imageHandle, offset?)`

Sets tab's image by already created handle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `imageHandle` | `integer` |  |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional image offset. |

**Returns:** `nil`

### `_CMenuSliderFloat:Icon(icon, offset?)`

Sets widget's icon.\
[Icons list](https://fontawesome.com/search?o=r&s=solid&f=classic)

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `icon` | `string` | icon unicode. |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional icon offset. |

**Returns:** `nil`

### `_CMenuSliderFloat:SetCallback(callback, forceCall?)`

Sets widget's on change callback.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `callback` | `fun(this: CMenuSliderFloat):nil` | function to be called on widget change.\ |
| `forceCall` *(optional)* | `boolean` | Default: `false`. true if you want to call callback on widget creation. |

**Returns:** `nil`

### `_CMenuSliderFloat:UnsetCallback(callback)`

Removes widget's on change callback.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `callback` | `fun(this: CMenuSliderFloat):nil` | function to be removed from widget's callbacks. |

**Returns:** `nil`

### `_CMenuSliderFloat:ColorPicker(name, color)`

Creates `CMenuColorPickerAttachment` and attaches it to the widget.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Name of the attachment. |
| `color` | `Color` | Default color. |

**Returns:** `CMenuColorPickerAttachment`

### `_CMenuSliderFloat:Gear(name, gearIcon?, useSmallFont?)`

Creates `CMenuGearAttachment` and attaches it to the widget.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Name of the attachment. |
| `gearIcon` *(optional)* | `string` | Default: `"\uf013"`. Gear FontAwesome icon. |
| `useSmallFont` *(optional)* | `boolean` | Default: `true`. Use small font for gear icon. |

**Returns:** `CMenuGearAttachment`
