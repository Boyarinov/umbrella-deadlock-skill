# CMenuMultiSelect

## CMenuMultiSelect

CMenuMultiSelect metatable.

### `_CMenuMultiSelect:Name()`

Returns widget's name.

**Returns:** `string`

### `_CMenuMultiSelect:Update(items, expanded?, saveToConfig?)`

Updates the multiselect values.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `items` | `{nameId: string, imagePath: string, isEnabled: boolean}[]` | See `CMenuGroup:MultiSelect`. |
| `expanded` *(optional)* | `boolean` | Default: `false`. false if you want to create MultiSelect in collapsed state. |
| `saveToConfig` *(optional)* | `boolean` | Default: `false`. true if you want to save to config |

**Returns:** `nil`

### `_CMenuMultiSelect:OneItemSelection(newState)`

Gets or sets one item selection state. One item selection allows only one item to be\
selected. Depends on the argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `newState` | `boolean` |  |

**Returns:** `boolean`

**Overloads:**

- `fun(this: CMenuMultiSelect):boolean`

### `_CMenuMultiSelect:DragAllowed(newState)`

Gets or sets drag allowed state. Drag allows items to be ordered by cursor.\
Depends on the argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `newState` | `boolean` |  |

**Returns:** `boolean`

**Overloads:**

- `fun(this: CMenuMultiSelect):boolean`

### `_CMenuMultiSelect:Parent()`

Returns widget's parent.

**Returns:** `CMenuGroup|CMenuGearAttachment`

### `_CMenuMultiSelect:Type()`

Returns widget type.

**Returns:** `Enum.WidgetType`

### `_CMenuMultiSelect:Open()`

Opens parent tabs.

**Returns:** `nil`

### `_CMenuMultiSelect:ForceLocalization(newText)`

Changes text in the widget. The path to the widget is not affected.\
May be used for dynamic text customization or recolor.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `newText` | `string` |  |

**Returns:** `nil`

### `_CMenuMultiSelect:ToolTip(newText)`

Gets or sets tooltip. Tooltip is displayed when mouse cursor is over the widget.\
Depends on the argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `newText` | `string` |  |

**Returns:** `string`

**Overloads:**

- `fun(this: CMenuMultiSelect):string`

### `_CMenuMultiSelect:Visible(value)`

Gets or sets visible state. Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuMultiSelect): boolean`

### `_CMenuMultiSelect:Disabled(value)`

Gets or sets disabled state. Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuMultiSelect): boolean`

### `_CMenuMultiSelect:Unsafe(value)`

Gets or sets unsafe state. Unsafe widgets have warning sign.\
Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuMultiSelect): boolean`

### `_CMenuMultiSelect:Get(itemId)`

Returns enable state of the item in multiselect.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `itemId` | `string` |  |

**Returns:** `boolean`

### `_CMenuMultiSelect:Set(enabledItems)`

Sets a new value for the item by itemId or sets a new list of enabled items

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `enabledItems` | `string[]` | A table of enabled items; other items will be disabled. |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuMultiSelect, itemId: string, value: boolean):nil`

### `_CMenuMultiSelect:List()`

Returns array of itemIds.

**Returns:** `string[]`

### `_CMenuMultiSelect:ListEnabled()`

Returns array of enabled itemIds.

**Returns:** `string[]`

### `_CMenuMultiSelect:Image(imagePath, offset?)`

Sets widget's image.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `imagePath` | `string` | Path to the image. |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional image offset. |

**Returns:** `nil`

### `_CMenuMultiSelect:ImageHandle(imageHandle, offset?)`

Sets tab's image by already created handle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `imageHandle` | `integer` |  |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional image offset. |

**Returns:** `nil`

### `_CMenuMultiSelect:Icon(icon, offset?)`

Sets widget's icon.\
[Icons list](https://fontawesome.com/search?o=r&s=solid&f=classic)

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `icon` | `string` | icon unicode. |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional icon offset. |

**Returns:** `nil`

### `_CMenuMultiSelect:SetCallback(callback, forceCall?)`

Sets widget's on change callback.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `callback` | `fun(this: CMenuMultiSelect):nil` | function to be called on widget change. |
| `forceCall` *(optional)* | `boolean` | Default: `false`. true if you want to call callback on widget creation. |

**Returns:** `nil`

### `_CMenuMultiSelect:UnsetCallback(callback)`

Removes widget's on change callback.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `callback` | `fun(this: CMenuMultiSelect):nil` | function to be removed from widget's callbacks. |

**Returns:** `nil`

### `_CMenuMultiSelect:UpdateBackgroundColors(colors)`

Updates widget's background colors.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `colors` | `table<string>` | Table with background colors. |

**Returns:** `nil`

### `_CMenuMultiSelect:UpdateImageColors(colors)`

Updates widget's image colors.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `colors` | `table<string>` | Table with image colors. |

**Returns:** `nil`

### `_CMenuMultiSelect:UpdateToolTips(colors)`

Updates widget's tooltips

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `colors` | `table<string>` | Table with new tooltips |

**Returns:** `nil`
