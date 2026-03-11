# Menu System

### `Menu.Find(firstTabName, sectionName, secondTabName, thirdTabName, groupTabName, widgetName, attachmentName, widgetInGearName)`

Returns menu item.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `firstTabName` | `string` |  |
| `sectionName` | `string` |  |
| `secondTabName` | `string` |  |
| `thirdTabName` | `string` |  |
| `groupTabName` | `string` |  |
| `widgetName` | `string` |  |
| `attachmentName` | `string` |  |
| `widgetInGearName` | `string` |  |

**Returns:** `CMenuSwitch|CMenuBind|CMenuSliderFloat|CMenuSliderInt|CMenuColorPicker|CMenuComboBox|CMenuButton|CMenuMultiComboBox|CMenuMultiSelect|CMenuInputBox|CMenuLabel|nil`

**Overloads:**

- `fun(firstTabName: string): CFirstTab|nil`
- `fun(firstTabName: string, sectionName: string): CTabSection|nil`
- `fun(firstTabName: string, sectionName: string, secondTabName: string): CSecondTab|nil`
- `fun(firstTabName: string, sectionName: string, secondTabName: string, thirdTabName: string): CThirdTab|nil`
- `fun(firstTabName: string, sectionName: string, secondTabName: string, thirdTabName: string, groupTabName: string): CMenuGroup|nil`
- `fun(firstTabName: string, sectionName: string, secondTabName: string, thirdTabName:string, groupTabName: string, widgetName: string): CMenuSwitch|CMenuBind|CMenuSliderFloat|CMenuSliderInt|CMenuColorPicker|CMenuComboBox|CMenuButton|CMenuMultiComboBox|CMenuMultiSelect|CMenuInputBox|CMenuLabel|nil`
- `fun(firstTabName: string, sectionName: string, secondTabName: string, thirdTabName: string, groupTabName: string, widgetName: string, attachmentName: string): CMenuGearAttachment|CMenuColorPickerAttachment|nil`

### `Menu.Create(firstTabName, sectionName, secondTabName, thirdTabName, groupTabName)`

Creates tab/section/group. Returns menu item.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `firstTabName` | `string` |  |
| `sectionName` | `string` |  |
| `secondTabName` | `string` |  |
| `thirdTabName` | `string` |  |
| `groupTabName` | `string` |  |

**Returns:** `CMenuGroup`

**Overloads:**

- `fun(firstTabName: string): CFirstTab`
- `fun(firstTabName: string, sectionName: string): CTabSection`
- `fun(firstTabName: string, sectionName: string, secondTabName: string): CSecondTab`
- `fun(firstTabName: string, sectionName: string, secondTabName: string, thirdTabName: string): CThirdTab`

### `Menu.Style(styleColor)`

Creates tab/section/group. Returns color of specified style var or table of all style colors\
depends on param.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `styleColor` | `string` |  |

**Returns:** `Color`

**Overloads:**

- `fun(): table`

### `Menu.Opened()`

Returns current menu open state.

**Returns:** `boolean`

### `Menu.Alpha()`

Returns current menu alpha.

**Returns:** `number`

### `Menu.Pos()`

Returns current menu pos.

**Returns:** `Vec2`

### `Menu.Size()`

Returns current menu size.

**Returns:** `Vec2`

### `Menu.Scale()`

Returns current menu scale percentage.

**Returns:** `integer`

### `Menu.AnimDuration()`

Returns current menu animation duration.

**Returns:** `number`

## CFirstTab

CFirstTab metatable

### `_CFirstTab:Name()`

Returns tab's name.

**Returns:** `string`

### `_CFirstTab:Parent()`

Returns parent. It's `nil` for CFirstTab.

**Returns:** `nil`

### `_CFirstTab:Type()`

Returns widget type.

**Returns:** `Enum.WidgetType`

### `_CFirstTab:Open()`

Opens parent tabs.

**Returns:** `nil`

### `_CFirstTab:Create(sectionName)`

Creates new `CTabSection`.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `sectionName` | `string` |  |

**Returns:** `CTabSection`

### `_CFirstTab:Find(sectionName)`

Finds the `CTabSection` by name.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `sectionName` | `string` |  |

**Returns:** `CTabSection|nil`

## CTabSection

CTabSection metatable

### `_CTabSection:Name()`

Returns tab's name.

**Returns:** `string`

### `_CTabSection:Parent()`

Returns tab's parent.

**Returns:** `CFirstTab`

### `_CTabSection:Type()`

Returns widget type.

**Returns:** `Enum.WidgetType`

### `_CTabSection:Open()`

Opens parent tabs.

**Returns:** `nil`

### `_CTabSection:Create(sectionName)`

Creates new `CSecondTab`.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `sectionName` | `string` |  |

**Returns:** `CSecondTab`

### `_CTabSection:Find(sectionName)`

Finds the `CSecondTab` by name.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `sectionName` | `string` |  |

**Returns:** `CSecondTab|nil`

## CSecondTab

CSecondTab metatable

### `_CSecondTab:Name()`

Returns tab's name.

**Returns:** `string`

### `_CSecondTab:Parent()`

Returns tab's parent.

**Returns:** `CTabSection`

### `_CSecondTab:Type()`

Returns widget type.

**Returns:** `Enum.WidgetType`

### `_CSecondTab:Open()`

Opens parent tabs.

**Returns:** `nil`

### `_CSecondTab:Create(tabName)`

Creates new `CThirdTab`.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `tabName` | `string` |  |

**Returns:** `CThirdTab`

### `_CSecondTab:Find(tabName)`

Finds the `CThirdTab` by name.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `tabName` | `string` |  |

**Returns:** `CThirdTab|nil`

### `_CSecondTab:Image(imagePath, offset?)`

Sets tab's image.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `imagePath` | `string` | Path to the image. |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional image offset. |

**Returns:** `nil`

### `_CSecondTab:ImageHandle(imageHandle, offset?)`

Sets tab's image by already created handle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `imageHandle` | `integer` |  |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional image offset. |

**Returns:** `nil`

### `_CSecondTab:Icon(icon, offset?)`

Sets tab's icon.\
[Icons list](https://fontawesome.com/search?o=r&s=solid&f=classic)

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `icon` | `string` | icon unicode. |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional icon offset. |

**Returns:** `nil`

### `_CSecondTab:LinkHero(heroId, attribute)`

Links tab to hero and attribute.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `heroId` | `integer` | See `ent.m_CCitadelHeroComponent.m_spawnedHero.m_nHeroID.m_Value` |
| `attribute` | `integer` |  |

**Returns:** `nil`

## CThirdTab

CThirdTab metatable

### `_CThirdTab:Name()`

Returns tab's name.

**Returns:** `string`

### `_CThirdTab:Parent()`

Returns tab's parent.

**Returns:** `CSecondTab`

### `_CThirdTab:Type()`

Returns widget type.

**Returns:** `Enum.WidgetType`

### `_CThirdTab:Open()`

Opens parent tabs.

**Returns:** `nil`

### `_CThirdTab:Create(groupName, side?)`

Creates new `CMenuGroup`.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `groupName` | `string` |  |
| `side` *(optional)* | `Enum.GroupSide` | Default: `Enum.GroupSide.Default` |

**Returns:** `CMenuGroup`

### `_CThirdTab:Find(groupName)`

Finds the `CMenuGroup` by name.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `groupName` | `string` |  |

**Returns:** `CMenuGroup|nil`

### `_CThirdTab:Image(imagePath, offset?)`

Sets tab's image.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `imagePath` | `string` | Path to the image. |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional image offset. |

**Returns:** `nil`

### `_CThirdTab:ImageHandle(imageHandle, offset?)`

Sets tab's image by already created handle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `imageHandle` | `integer` |  |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional image offset. |

**Returns:** `nil`

### `_CThirdTab:Icon(icon, offset?)`

Sets tab's icon.\
[Icons list](https://fontawesome.com/search?o=r&s=solid&f=classic)

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `icon` | `string` | icon unicode. |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional icon offset. |

**Returns:** `nil`

## CMenuGroup

CMenuGroup metatable

### `_CMenuGroup:Name()`

Returns group's name.

**Returns:** `string`

### `_CMenuGroup:Parent()`

Returns group's parent.

**Returns:** `CThirdTab`

### `_CMenuGroup:Type()`

Returns widget type.

**Returns:** `Enum.WidgetType`

### `_CMenuGroup:Open()`

Opens parent tabs.

**Returns:** `nil`

### `_CMenuGroup:Find(widgetName)`

Finds the widget by name.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `widgetName` | `string` |  |

**Returns:** `CMenuSwitch|CMenuBind|CMenuSliderFloat|CMenuSliderInt|CMenuColorPicker|CMenuComboBox|CMenuButton|CMenuMultiComboBox|CMenuMultiSelect|CMenuInputBox|CMenuLabel|nil`

### `_CMenuGroup:Switch(switchName, defaultValue?, imageIcon?)`

Creates new `CMenuSwitch`.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `switchName` | `string` |  |
| `defaultValue` *(optional)* | `boolean` | Default: `false` |
| `imageIcon` *(optional)* | `string` | Default: `""`. Path to image or FontAwesome icon unicode. |

**Returns:** `CMenuSwitch`

### `_CMenuGroup:Bind(bindName, defaultValue?, imageIcon?)`

Creates new `CMenuBind`.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `bindName` | `string` |  |
| `defaultValue` *(optional)* | `Enum.ButtonCode` | Default: `Enum.ButtonCode.BUTTON_CODE_INVALID` |
| `imageIcon` *(optional)* | `string` | Default: `""`. Path to image or FontAwesome icon unicode. |

**Returns:** `CMenuBind`

### `_CMenuGroup:Slider(sliderName, minValue, maxValue, defaultValue, format?)`

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

- `fun(this: CMenuGroup, sliderName: string, minValue: number, maxValue: number, defaultValue: number, format: string|fun(value: number):string): CMenuSliderFloat`

### `_CMenuGroup:ColorPicker(colorPickerName, color, imageIcon?)`

Creates new `CMenuColorPicker`.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `colorPickerName` | `string` |  |
| `color` | `Color` |  |
| `imageIcon` *(optional)* | `string` | Default: `""`. Path to image or FontAwesome icon unicode. |

**Returns:** `CMenuColorPicker`

### `_CMenuGroup:Button(buttonName, callback, altStyle?, widthPercent?)`

Creates new `CMenuButton`.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `buttonName` | `string` |  |
| `callback` | `function` | `fun(this: CMenuButton):nil` function to call on button click. |
| `altStyle` *(optional)* | `boolean` | Default: `false`. Use alternative button style. |
| `widthPercent` *(optional)* | `number` | Default: `1.0`. Button width in percents. [0.0, 1.0] |

**Returns:** `CMenuButton`

### `_CMenuGroup:Combo(comboName, items, defaultValue?)`

Creates new `CMenuComboBox`.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `comboName` | `string` |  |
| `items` | `string[]` |  |
| `defaultValue` *(optional)* | `integer` | Default: `0`. Index of default item. (starts from 0) |

**Returns:** `CMenuComboBox`

### `_CMenuGroup:MultiCombo(multiComboName, items, enabledItems)`

Creates new `CMenuMultiComboBox`.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `multiComboName` | `string` |  |
| `items` | `string[]` |  |
| `enabledItems` | `string[]` | table of enabled items |

**Returns:** `CMenuMultiComboBox`

### `_CMenuGroup:MultiSelect(multiSelectName, items, expanded?)`

Creates new `CMenuMultiSelect`.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `multiSelectName` | `string` |  |
| `items` | `{nameId: string, imagePath: string, isEnabled: boolean}[]` | See example. |
| `expanded` *(optional)* | `boolean` | Default: `false`. false if you want to create MultiSelect in collapsed state. |

**Returns:** `CMenuMultiSelect`

### `_CMenuGroup:Input(inputName, defaultValue, imageIcon?)`

Creates new `CMenuInputBox`.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `inputName` | `string` |  |
| `defaultValue` | `string` |  |
| `imageIcon` *(optional)* | `string` | Default: `""`. Path to image or FontAwesome icon unicode. |

**Returns:** `CMenuInputBox`

### `_CMenuGroup:Label(labelText, imageIcon?)`

Creates new `CMenuLabel`.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `labelText` | `string` |  |
| `imageIcon` *(optional)* | `string` | Default: `""`. Path to image or FontAwesome icon unicode. |

**Returns:** `CMenuLabel`

### `_CMenuGroup:Disabled(value)`

Gets or sets group's disabled state. Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuGroup): boolean`

### `_CMenuGroup:Visible(value)`

Gets or sets group's visible state. Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuGroup): boolean`

### `_CMenuGroup:SearchHidden(value)`

Gets or sets group's search state. Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuGroup): boolean`


## Widgets

Each widget type has its own reference page:

| Widget | Description | Reference |
|--------|-------------|-----------|
| `CMenuSwitch` | CMenuSwitch metatable. | [Reference](menu/switch.md) |
| `CMenuBind` | CMenuBind metatable. | [Reference](menu/bind.md) |
| `CMenuButton` | CMenuButton metatable. | [Reference](menu/button.md) |
| `CMenuSliderFloat` | CMenuSliderFloat metatable. | [Reference](menu/slider-float.md) |
| `CMenuSliderInt` | CMenuSliderInt metatable. | [Reference](menu/slider-int.md) |
| `CMenuColorPicker` | CMenuColorPicker metatable. | [Reference](menu/color-picker.md) |
| `CMenuColorPickerAttachment` | CMenuColorPickerAttachment metatable. | [Reference](menu/color-picker-attachment.md) |
| `CMenuComboBox` | CMenuComboBox metatable. | [Reference](menu/combo-box.md) |
| `CMenuMultiComboBox` | CMenuMultiComboBox metatable. | [Reference](menu/multi-combo-box.md) |
| `CMenuMultiSelect` | CMenuMultiSelect metatable. | [Reference](menu/multi-select.md) |
| `CMenuInputBox` | CMenuInputBox metatable. | [Reference](menu/input-box.md) |
| `CMenuLabel` | CMenuLabel metatable. | [Reference](menu/label.md) |
| `CMenuGearAttachment` | CMenuGearAttachment metatable. | [Reference](menu/gear-attachment.md) |
