# CMenuBind

## CMenuBind

CMenuBind metatable.

### `_CMenuBind:Name()`

Returns widget's name.

**Returns:** `string`

### `_CMenuBind:Parent()`

Returns widget's parent.

**Returns:** `CMenuGroup|CMenuGearAttachment`

### `_CMenuBind:Type()`

Returns widget's type.

**Returns:** `Enum.WidgetType`

### `_CMenuBind:Open()`

Opens parent tabs.

**Returns:** `nil`

### `_CMenuBind:ForceLocalization(newText)`

Changes text in the widget. The path to the widget is not affected.\
May be used for dynamic text customization or recolor.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `newText` | `string` |  |

**Returns:** `nil`

### `_CMenuBind:ToolTip(newText)`

Gets or sets tooltip. Tooltip is displayed when mouse cursor is over the widget.\
Depends on the argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `newText` | `string` |  |

**Returns:** `string`

**Overloads:**

- `fun(this: CMenuBind):string`

### `_CMenuBind:Visible(value)`

Gets or sets visible state. Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuBind): boolean`

### `_CMenuBind:Disabled(value)`

Gets or sets disabled state. Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuBind): boolean`

### `_CMenuBind:Unsafe(value)`

Gets or sets unsafe state. Unsafe widgets have warning sign.\
Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuBind): boolean`

### `_CMenuBind:Get(idx?)`

Returns widget's value. To get both of the buttons use `Buttons` method.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `idx` *(optional)* | `0\|1` | Default: `0`. index of the button to get value from |

**Returns:** `Enum.ButtonCode`

### `_CMenuBind:Set(key1, key2?)`

Sets widget's value.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `key1` | `Enum.ButtonCode` | primary button code |
| `key2` *(optional)* | `Enum.ButtonCode` | Default: `Enum.ButtonCode.KEY_NONE`. secondary button code |

**Returns:** `nil`

### `_CMenuBind:Buttons()`

Returns widget's buttons value.

**Returns:** `Enum.ButtonCode` — first button code, `Enum.ButtonCode` — second button code

### `_CMenuBind:IsDown()`

Returns `true` when the key or both keys is down.

**Returns:** `boolean`

### `_CMenuBind:IsPressed()`

Returns `true` when the key or both keys is pressed for the first time.

**Returns:** `boolean`

### `_CMenuBind:IsToggled()`

Bind stores it's toggle state and switches it when the key is pressed. This method\
returns this state.

**Returns:** `boolean`

### `_CMenuBind:SetToggled(value)`

Sets the toggle state manually.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

### `_CMenuBind:Image(imagePath, offset?)`

Sets widget's image.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `imagePath` | `string` | Path to the image. |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional image offset. |

**Returns:** `nil`

### `_CMenuBind:ImageHandle(imageHandle, offset?)`

Sets tab's image by already created handle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `imageHandle` | `integer` |  |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional image offset. |

**Returns:** `nil`

### `_CMenuBind:Icon(icon, offset?)`

Sets widget's icon.\
[Icons list](https://fontawesome.com/search?o=r&s=solid&f=classic)

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `icon` | `string` | icon unicode. |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional icon offset. |

**Returns:** `nil`

### `_CMenuBind:SetCallback(callback, forceCall?)`

Sets widget's on change callback.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `callback` | `fun(this: CMenuBind):nil` | function to be called on widget change. |
| `forceCall` *(optional)* | `boolean` | Default: `false`. true if you want to call callback on widget creation. |

**Returns:** `nil`

### `_CMenuBind:UnsetCallback(callback)`

Removes widget's on change callback.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `callback` | `fun(this: CMenuBind):nil` | function to be removed from widget's callbacks. |

**Returns:** `nil`

### `_CMenuBind:ColorPicker(name, color)`

Creates `CMenuColorPickerAttachment` and attaches it to the widget.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Name of the attachment. |
| `color` | `Color` | Default color. |

**Returns:** `CMenuColorPickerAttachment`

### `_CMenuBind:Gear(name, gearIcon?, useSmallFont?)`

Creates `CMenuGearAttachment` and attaches it to the widget.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Name of the attachment. |
| `gearIcon` *(optional)* | `string` | Default: `"\uf013"`. Gear FontAwesome icon. |
| `useSmallFont` *(optional)* | `boolean` | Default: `true`. Use small font for gear icon. |

**Returns:** `CMenuGearAttachment`

### `_CMenuBind:Properties(name?, value?, markAsToggle?)`

Updates the properties of a widget for display in the bind list.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` *(optional)* | `string` | Default: `nil`. Overridden name to display in bind list. |
| `value` *(optional)* | `string` | Default: `nil`. Overridden value to display alongside the name in the bind list. This can be used to provide additional context about the bind. |
| `markAsToggle` *(optional)* | `boolean` | Default: `false`. Indicates whether the bind should be marked as a toggle, which is particularly useful if the bind's functionality includes toggling states. Recommended to be used in conjunction with the IsToggled(). |

**Returns:** `nil`

### `_CMenuBind:ShowInBindIsland(newStatus)`

Gets or sets the visibility of the bind in the bind island.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `newStatus` | `boolean` |  |

**Returns:** `boolean`

**Overloads:**

- `fun(this: CMenuBind):boolean`

### `_CMenuBind:MouseBinding(newStatus)`

Gets or sets the ability to bind the mouse button.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `newStatus` | `boolean` |  |

**Returns:** `boolean`

**Overloads:**

- `fun(this: CMenuBind):boolean`
