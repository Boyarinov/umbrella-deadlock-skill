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

## CMenuSwitch

CMenuSwitch metatable.

### `_CMenuSwitch:Name()`

Returns widget's name.

**Returns:** `string`

### `_CMenuSwitch:Parent()`

Returns widget's parent.

**Returns:** `CMenuGroup|CMenuGearAttachment`

### `_CMenuSwitch:Type()`

Returns widget type.

**Returns:** `Enum.WidgetType`

### `_CMenuSwitch:Open()`

Opens parent tabs.

**Returns:** `nil`

### `_CMenuSwitch:ForceLocalization(newText)`

Changes text in the widget. The path to the widget is not affected.\
May be used for dynamic text customization or recolor.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `newText` | `string` |  |

**Returns:** `nil`

### `_CMenuSwitch:ToolTip(newText)`

Gets or sets tooltip. Tooltip is displayed when mouse cursor is over the widget.\
Depends on the argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `newText` | `string` |  |

**Returns:** `string`

**Overloads:**

- `fun(this: CMenuSwitch):string`

### `_CMenuSwitch:Visible(value)`

Gets or sets visible state. Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuSwitch): boolean`

### `_CMenuSwitch:Disabled(value)`

Gets or sets disabled state. Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuSwitch): boolean`

### `_CMenuSwitch:Unsafe(value)`

Gets or sets unsafe state. Unsafe widgets have warning sign.\
Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuSwitch): boolean`

### `_CMenuSwitch:Get()`

Returns widget's value.

**Returns:** `boolean`

### `_CMenuSwitch:Set(value)`

Sets widget's value.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

### `_CMenuSwitch:Image(imagePath, offset?)`

Sets widget's image.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `imagePath` | `string` | Path to the image. |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional image offset. |

**Returns:** `nil`

### `_CMenuSwitch:ImageHandle(imageHandle, offset?)`

Sets tab's image by already created handle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `imageHandle` | `integer` |  |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional image offset. |

**Returns:** `nil`

### `_CMenuSwitch:Icon(icon, offset?)`

Sets widget's icon.\
[Icons list](https://fontawesome.com/search?o=r&s=solid&f=classic)

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `icon` | `string` | icon unicode. |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional icon offset. |

**Returns:** `nil`

### `_CMenuSwitch:SetCallback(callback, forceCall?)`

Sets widget's on change callback.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `callback` | `fun(this: CMenuSwitch):nil` | function to be called on widget change. |
| `forceCall` *(optional)* | `boolean` | Default: `false`. true if you want to call callback on widget creation. |

**Returns:** `nil`

### `_CMenuSwitch:UnsetCallback(callback)`

Removes widget's on change callback.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `callback` | `fun(this: CMenuSwitch):nil` | function to be removed from widget's callbacks. |

**Returns:** `nil`

### `_CMenuSwitch:ColorPicker(name, color)`

Creates `CMenuColorPickerAttachment` and attaches it to the widget.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Name of the attachment. |
| `color` | `Color` | Default color. |

**Returns:** `CMenuColorPickerAttachment`

### `_CMenuSwitch:Gear(name, gearIcon?, useSmallFont?)`

Creates `CMenuGearAttachment` and attaches it to the widget.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Name of the attachment. |
| `gearIcon` *(optional)* | `string` | Default: `"\uf013"`. Gear FontAwesome icon. |
| `useSmallFont` *(optional)* | `boolean` | Default: `true`. Use small font for gear icon. |

**Returns:** `CMenuGearAttachment`

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

## CMenuButton

CMenuButton metatable.

### `_CMenuButton:Name()`

Returns widget's name.

**Returns:** `string`

### `_CMenuButton:Parent()`

Returns widget's parent.

**Returns:** `CMenuGroup|CMenuGearAttachment`

### `_CMenuButton:Type()`

Returns widget type.

**Returns:** `Enum.WidgetType`

### `_CMenuButton:Open()`

Opens parent tabs.

**Returns:** `nil`

### `_CMenuButton:ForceLocalization(newText)`

Changes text in the widget. The path to the widget is not affected.\
May be used for dynamic text customization or recolor.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `newText` | `string` |  |

**Returns:** `nil`

### `_CMenuButton:ToolTip(newText)`

Gets or sets tooltip. Tooltip is displayed when mouse cursor is over the widget.\
Depends on the argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `newText` | `string` |  |

**Returns:** `string`

**Overloads:**

- `fun(this: CMenuButton):string`

### `_CMenuButton:Visible(value)`

Gets or sets visible state. Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuButton): boolean`

### `_CMenuButton:Disabled(value)`

Gets or sets disabled state. Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuButton): boolean`

### `_CMenuButton:Unsafe(value)`

Gets or sets unsafe state. Unsafe widgets have warning sign.\
Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuButton): boolean`

### `_CMenuButton:Image(imagePath, offset?)`

Sets widget's image.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `imagePath` | `string` | Path to the image. |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional image offset. |

**Returns:** `nil`

### `_CMenuButton:ImageHandle(imageHandle, offset?)`

Sets tab's image by already created handle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `imageHandle` | `integer` |  |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional image offset. |

**Returns:** `nil`

### `_CMenuButton:Icon(icon, offset?)`

Sets widget's icon.\
[Icons list](https://fontawesome.com/search?o=r&s=solid&f=classic)

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `icon` | `string` | icon unicode. |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional icon offset. |

**Returns:** `nil`

### `_CMenuButton:SetCallback(callback, forceCall?)`

Sets widget's on change callback.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `callback` | `fun(this: CMenuButton):nil` | function to be called on widget change. |
| `forceCall` *(optional)* | `boolean` | Default: `false`. true if you want to call callback on widget creation. |

**Returns:** `nil`

### `_CMenuButton:UnsetCallback(callback)`

Removes widget's on change callback.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `callback` | `fun(this: CMenuButton):nil` | function to be removed from widget's callbacks. |

**Returns:** `nil`

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

## CMenuSliderInt

CMenuSliderInt metatable.

### `_CMenuSliderInt:Update(minValue, maxValue, defaultValue)`

Updates the slider values.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `minValue` | `integer` |  |
| `maxValue` | `integer` |  |
| `defaultValue` | `integer` |  |

**Returns:** `nil`

### `_CMenuSliderInt:Name()`

Returns widget's name.

**Returns:** `string`

### `_CMenuSliderInt:Parent()`

Returns widget's parent.

**Returns:** `CMenuGroup|CMenuGearAttachment`

### `_CMenuSliderInt:Type()`

Returns widget type.

**Returns:** `Enum.WidgetType`

### `_CMenuSliderInt:Open()`

Opens parent tabs.

**Returns:** `nil`

### `_CMenuSliderInt:ForceLocalization(newText)`

Changes text in the widget. The path to the widget is not affected.\
May be used for dynamic text customization or recolor.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `newText` | `string` |  |

**Returns:** `nil`

### `_CMenuSliderInt:ToolTip(newText)`

Gets or sets tooltip. Tooltip is displayed when mouse cursor is over the widget.\
Depends on the argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `newText` | `string` |  |

**Returns:** `string`

**Overloads:**

- `fun(this: CMenuSliderInt):string`

### `_CMenuSliderInt:Visible(value)`

Gets or sets visible state. Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuSliderInt): boolean`

### `_CMenuSliderInt:Disabled(value)`

Gets or sets disabled state. Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuSliderInt): boolean`

### `_CMenuSliderInt:Unsafe(value)`

Gets or sets unsafe state. Unsafe widgets have warning sign.\
Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuSliderInt): boolean`

### `_CMenuSliderInt:Get()`

Returns widget's value.

**Returns:** `integer`

### `_CMenuSliderInt:Set(value)`

Sets widget's value.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `integer` |  |

**Returns:** `nil`

### `_CMenuSliderInt:Image(imagePath, offset?)`

Sets widget's image.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `imagePath` | `string` | Path to the image. |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional image offset. |

**Returns:** `nil`

### `_CMenuSliderInt:ImageHandle(imageHandle, offset?)`

Sets tab's image by already created handle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `imageHandle` | `integer` |  |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional image offset. |

**Returns:** `nil`

### `_CMenuSliderInt:Icon(icon, offset?)`

Sets widget's icon.\
[Icons list](https://fontawesome.com/search?o=r&s=solid&f=classic)

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `icon` | `string` | icon unicode. |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional icon offset. |

**Returns:** `nil`

### `_CMenuSliderInt:SetCallback(callback, forceCall?)`

Sets widget's on change callback.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `callback` | `fun(this: CMenuSliderInt):nil` | function to be called on widget change. |
| `forceCall` *(optional)* | `boolean` | Default: `false`. true if you want to call callback on widget creation. |

**Returns:** `nil`

### `_CMenuSliderInt:UnsetCallback(callback)`

Removes widget's on change callback.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `callback` | `fun(this: CMenuSliderInt):nil` | function to be removed from widget's callbacks. |

**Returns:** `nil`

### `_CMenuSliderInt:ColorPicker(name, color)`

Creates `CMenuColorPickerAttachment` and attaches it to the widget.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Name of the attachment. |
| `color` | `Color` | Default color. |

**Returns:** `CMenuColorPickerAttachment`

### `_CMenuSliderInt:Gear(name, gearIcon?, useSmallFont?)`

Creates `CMenuGearAttachment` and attaches it to the widget.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Name of the attachment. |
| `gearIcon` *(optional)* | `string` | Default: `"\uf013"`. Gear FontAwesome icon. |
| `useSmallFont` *(optional)* | `boolean` | Default: `true`. Use small font for gear icon. |

**Returns:** `CMenuGearAttachment`

## CMenuColorPicker

CMenuColorPicker metatable.

### `_CMenuColorPicker:Name()`

Returns widget's name.

**Returns:** `string`

### `_CMenuColorPicker:Parent()`

Returns widget's parent.

**Returns:** `CMenuGroup|CMenuGearAttachment`

### `_CMenuColorPicker:Type()`

Returns widget type.

**Returns:** `Enum.WidgetType`

### `_CMenuColorPicker:Open()`

Opens parent tabs.

**Returns:** `nil`

### `_CMenuColorPicker:ForceLocalization(newText)`

Changes text in the widget. The path to the widget is not affected.\
May be used for dynamic text customization or recolor.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `newText` | `string` |  |

**Returns:** `nil`

### `_CMenuColorPicker:ToolTip(newText)`

Gets or sets tooltip. Tooltip is displayed when mouse cursor is over the widget.\
Depends on the argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `newText` | `string` |  |

**Returns:** `string`

**Overloads:**

- `fun(this: CMenuColorPicker):string`

### `_CMenuColorPicker:Visible(value)`

Gets or sets visible state. Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuColorPicker): boolean`

### `_CMenuColorPicker:Disabled(value)`

Gets or sets disabled state. Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuColorPicker): boolean`

### `_CMenuColorPicker:Unsafe(value)`

Gets or sets unsafe state. Unsafe widgets have warning sign.\
Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuColorPicker): boolean`

### `_CMenuColorPicker:Get()`

Returns widget's value.

**Returns:** `Color`

### `_CMenuColorPicker:Set(value)`

Sets widget's value.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `Color` |  |

**Returns:** `nil`

### `_CMenuColorPicker:Image(imagePath, offset?)`

Sets widget's image.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `imagePath` | `string` | Path to the image. |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional image offset. |

**Returns:** `nil`

### `_CMenuColorPicker:ImageHandle(imageHandle, offset?)`

Sets tab's image by already created handle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `imageHandle` | `integer` |  |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional image offset. |

**Returns:** `nil`

### `_CMenuColorPicker:Icon(icon, offset?)`

Sets widget's icon.\
[Icons list](https://fontawesome.com/search?o=r&s=solid&f=classic)

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `icon` | `string` | icon unicode. |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional icon offset. |

**Returns:** `nil`

### `_CMenuColorPicker:ImageHandle(imageHandle, offset?)`

Sets tab's image by already created handle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `imageHandle` | `integer` |  |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional image offset. |

**Returns:** `nil`

### `_CMenuColorPicker:SetCallback(callback, forceCall?)`

Sets widget's on change callback.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `callback` | `fun(this: CMenuColorPicker):nil` | function to be called on widget change. |
| `forceCall` *(optional)* | `boolean` | Default: `false`. true if you want to call callback on widget creation. |

**Returns:** `nil`

### `_CMenuColorPicker:UnsetCallback(callback)`

Removes widget's on change callback.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `callback` | `fun(this: CMenuColorPicker):nil` | function to be removed from widget's callbacks. |

**Returns:** `nil`

### `_CMenuColorPicker:HideAlphaBar(value)`

Gets or sets alpha bar state. Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuColorPicker): boolean`

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

## CMenuLabel

CMenuLabel metatable.

### `_CMenuLabel:Name()`

Returns widget's name.

**Returns:** `string`

### `_CMenuLabel:Parent()`

Returns widget's parent.

**Returns:** `CMenuGroup|CMenuGearAttachment`

### `_CMenuLabel:Type()`

Returns widget type.

**Returns:** `Enum.WidgetType`

### `_CMenuLabel:Open()`

Opens parent tabs.

**Returns:** `nil`

### `_CMenuLabel:ForceLocalization(newText)`

Changes text in the widget. The path to the widget is not affected.\
May be used for dynamic text customization or recolor.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `newText` | `string` |  |

**Returns:** `nil`

### `_CMenuLabel:ToolTip(newText)`

Gets or sets tooltip. Tooltip is displayed when mouse cursor is over the widget.\
Depends on the argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `newText` | `string` |  |

**Returns:** `string`

**Overloads:**

- `fun(this: CMenuLabel):string`

### `_CMenuLabel:Visible(value)`

Gets or sets visible state. Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuLabel): boolean`

### `_CMenuLabel:Disabled(value)`

Gets or sets disabled state. Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuLabel): boolean`

### `_CMenuLabel:Unsafe(value)`

Gets or sets unsafe state. Unsafe widgets have warning sign.\
Depends on argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` |  |

**Returns:** `nil`

**Overloads:**

- `fun(this: CMenuLabel): boolean`

### `_CMenuLabel:Image(imagePath, offset?)`

Sets widget's image.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `imagePath` | `string` | Path to the image. |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional image offset. |

**Returns:** `nil`

### `_CMenuLabel:ImageHandle(imageHandle, offset?)`

Sets tab's image by already created handle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `imageHandle` | `integer` |  |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional image offset. |

**Returns:** `nil`

### `_CMenuLabel:Icon(icon, offset?)`

Sets widget's icon.\
[Icons list](https://fontawesome.com/search?o=r&s=solid&f=classic)

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `icon` | `string` | icon unicode. |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. Optional icon offset. |

**Returns:** `nil`

### `_CMenuLabel:ColorPicker(name, color)`

Creates `CMenuColorPickerAttachment` and attaches it to the widget.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Name of the attachment. |
| `color` | `Color` | Default color. |

**Returns:** `CMenuColorPickerAttachment`

### `_CMenuLabel:Gear(name, gearIcon?, useSmallFont?)`

Creates `CMenuGearAttachment` and attaches it to the widget.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Name of the attachment. |
| `gearIcon` *(optional)* | `string` | Default: `"\uf013"`. Gear FontAwesome icon. |
| `useSmallFont` *(optional)* | `boolean` | Default: `true`. Use small font for gear icon. |

**Returns:** `CMenuGearAttachment`

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
