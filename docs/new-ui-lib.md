# UI Library

## ui_lib_element_gear

A gear-attached menu widget wrapper with chainable methods.

### Fields

| Name | Type | Description |
|------|------|-------------|
| `ref` | `CMenuSwitch\|CMenuSliderFloat\|CMenuSliderInt\|CMenuComboBox\|CMenuMultiComboBox\|CMenuMultiSelect\|CMenuInputBox\|CMenuBind\|CMenuButton\|CMenuLabel\|CMenuColorPicker\|CMenuGearAttachment` | Underlying menu reference. |
| `value` | `any` | Current widget value. |

### Methods

#### `ui_lib_element_gear:set(value)`

Sets the element value.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `any` | Value to set. |

**Returns:** `ui_lib_element_gear` — Self for chaining.

#### `ui_lib_element_gear:tooltip(text)`

Sets the tooltip text.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `text` | `string` | Tooltip text. |

**Returns:** `ui_lib_element_gear` — Self for chaining.

#### `ui_lib_element_gear:icon(icon)`

Sets the icon.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `icon` | `string` | Icon identifier. |

**Returns:** `ui_lib_element_gear` — Self for chaining.

#### `ui_lib_element_gear:image(image)`

Sets the image.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `image` | `string` | Image path or identifier. |

**Returns:** `ui_lib_element_gear` — Self for chaining.

#### `ui_lib_element_gear:visible(state)`

Sets visibility state.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `state` | `boolean` | Visible or hidden. |

#### `ui_lib_element_gear:disable(state)`

Sets disabled state.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `state` | `boolean` | Disabled or enabled. |

#### `ui_lib_element_gear:visible_condition(func)`

Sets a visibility condition function.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `func` | `fun(): boolean` | Condition returning true when visible. |

**Returns:** `ui_lib_element_gear` — Self for chaining.

#### `ui_lib_element_gear:disable_condition(func)`

Sets a disable condition function.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `func` | `fun(): boolean` | Condition returning true when disabled. |

**Returns:** `ui_lib_element_gear` — Self for chaining.

#### `ui_lib_element_gear:set_callback(func, preload?)`

Registers a callback on value change.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `func` | `function` | Callback function. |
| `preload` *(optional)* | `boolean` | Fire callback immediately with current value. |

**Returns:** `ui_lib_element_gear` — Self for chaining.

#### `ui_lib_element_gear:unset_callback(func)`

Removes a previously registered callback.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `func` | `function` | Callback to remove. |

**Returns:** `ui_lib_element_gear` — Self for chaining.

#### `ui_lib_element_gear:link_to_ui_disable_condition(ui_table)`

Links disable condition to another ui element table.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `ui_table` | `ui_lib_element` | Disable when this element is falsy. |

**Returns:** `ui_lib_element_gear` — Self for chaining.

#### `ui_lib_element_gear:link_to_ui_visible_condition(ui_table)`

Links visibility condition to another ui element table.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `ui_table` | `ui_lib_element` | Show only when this element is truthy. |

**Returns:** `ui_lib_element_gear` — Self for chaining.

## ui_lib_element

*Extends [`ui_lib_element_gear`](#ui_lib_element_gear)*

A top-level menu widget in a group, wraps gear-level widgets.

### Methods

#### `ui_lib_element:switch(name, def_value?, icon?, tooltip?)`

Creates a switch (toggle) gear element.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Display name. |
| `def_value` *(optional)* | `boolean` | Default value. |
| `icon` *(optional)* | `string` | Icon identifier. |
| `tooltip` *(optional)* | `string` | Tooltip text. |

**Returns:** `ui_lib_element_gear`

#### `ui_lib_element:slider(name, min, max, def_value?, format?, icon?, tooltip?)`

Creates a slider gear element.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Display name. |
| `min` | `number` | Minimum value. |
| `max` | `number` | Maximum value. |
| `def_value` *(optional)* | `number` | Default value. |
| `format` *(optional)* | `string` | Display format string (e.g. "%.2f°"). |
| `icon` *(optional)* | `string` | Icon identifier. |
| `tooltip` *(optional)* | `string` | Tooltip text. |

**Returns:** `ui_lib_element_gear`

#### `ui_lib_element:combo(name, array, def_value?, icon?, tooltip?)`

Creates a combo box gear element.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Display name. |
| `array` | `string[]` | List of options. |
| `def_value` *(optional)* | `integer` | Default selected index (1-based). |
| `icon` *(optional)* | `string` | Icon identifier. |
| `tooltip` *(optional)* | `string` | Tooltip text. |

**Returns:** `ui_lib_element_gear`

#### `ui_lib_element:multicombo(name, array, def_value?, icon?, tooltip?)`

Creates a multi-combo gear element.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Display name. |
| `array` | `string[]` | List of options. |
| `def_value` *(optional)* | `any` | Default value. |
| `icon` *(optional)* | `string` | Icon identifier. |
| `tooltip` *(optional)* | `string` | Tooltip text. |

**Returns:** `ui_lib_element_gear`

#### `ui_lib_element:multiselectable(name, array, expand?, icon?, tooltip?)`

Creates a multi-selectable gear element.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Display name. |
| `array` | `string[]` | List of options. |
| `expand` *(optional)* | `boolean` | Expand by default. |
| `icon` *(optional)* | `string` | Icon identifier. |
| `tooltip` *(optional)* | `string` | Tooltip text. |

**Returns:** `ui_lib_element_gear`

#### `ui_lib_element:button(name, icon?, func?, tooltip?)`

Creates a button gear element.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Display name. |
| `icon` *(optional)* | `string` | Icon identifier. |
| `func` *(optional)* | `function` | Click callback. |
| `tooltip` *(optional)* | `string` | Tooltip text. |

**Returns:** `ui_lib_element_gear`

#### `ui_lib_element:label(name, icon?, tooltip?)`

Creates a label gear element.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Display name. |
| `icon` *(optional)* | `string` | Icon identifier. |
| `tooltip` *(optional)* | `string` | Tooltip text. |

**Returns:** `ui_lib_element_gear`

#### `ui_lib_element:colorpicker(name, color, in_gear?, icon?, tooltip?)`

Creates a color picker gear element.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Display name. |
| `color` | `Color` | Default color. |
| `in_gear` *(optional)* | `boolean` | Attach inside the gear row. |
| `icon` *(optional)* | `string` | Icon identifier. |
| `tooltip` *(optional)* | `string` | Tooltip text. |

**Returns:** `ui_lib_element_gear`

#### `ui_lib_element:input(name, def_value?, icon?, tooltip?)`

Creates an input box gear element.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Display name. |
| `def_value` *(optional)* | `string` | Default text. |
| `icon` *(optional)* | `string` | Icon identifier. |
| `tooltip` *(optional)* | `string` | Tooltip text. |

**Returns:** `ui_lib_element_gear`

#### `ui_lib_element:bind(name, def_value?, icon?, tooltip?)`

Creates a key bind gear element.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Display name. |
| `def_value` *(optional)* | `integer` | Default key code. |
| `icon` *(optional)* | `string` | Icon identifier. |
| `tooltip` *(optional)* | `string` | Tooltip text. |

**Returns:** `ui_lib_element_gear`

#### `ui_lib_element:override_gear_name(name)`

Overrides the gear display name.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | New gear name. |

**Returns:** `ui_lib_element` — Self for chaining.

#### `ui_lib_element:override_gear_icon(icon)`

Overrides the gear icon.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `icon` | `string` | New gear icon. |

**Returns:** `ui_lib_element` — Self for chaining.

#### `ui_lib_element:override_gear_size(is_small)`

Overrides the gear size.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `is_small` | `boolean` | Use small gear layout. |

**Returns:** `ui_lib_element` — Self for chaining.

#### `ui_lib_element:down_once()`

Returns whether the bound key was pressed this frame (bind elements only).

**Returns:** `boolean`

#### `ui_lib_element:down()`

Returns whether the bound key is held down (bind elements only).

**Returns:** `boolean`

#### `ui_lib_element:toggle()`

Returns the toggle state of the bound key (bind elements only).

**Returns:** `boolean`

#### `ui_lib_element:set_toggle(value)`

Sets the toggle state for a bind element.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `boolean` | Toggle state. |

**Returns:** `ui_lib_element` — Self for chaining.

#### `ui_lib_element:list(only_enabled?)`

Returns the option list for combo/multicombo elements.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `only_enabled` *(optional)* | `boolean` | For multicombo, return only enabled entries. |

**Returns:** `string[]` — List of option names.

## ui_lib_group

A menu group containing widgets.

### Methods

#### `ui_lib_group:switch(name, def_value?, icon?, tooltip?)`

Creates a switch (toggle) element.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Display name. |
| `def_value` *(optional)* | `boolean` | Default value. |
| `icon` *(optional)* | `string` | Icon identifier. |
| `tooltip` *(optional)* | `string` | Tooltip text. |

**Returns:** `ui_lib_element`

#### `ui_lib_group:slider(name, min, max, def_value?, format?, icon?, tooltip?)`

Creates a slider element.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Display name. |
| `min` | `number` | Minimum value. |
| `max` | `number` | Maximum value. |
| `def_value` *(optional)* | `number` | Default value. |
| `format` *(optional)* | `string` | Display format string (e.g. "%.2f°"). |
| `icon` *(optional)* | `string` | Icon identifier. |
| `tooltip` *(optional)* | `string` | Tooltip text. |

**Returns:** `ui_lib_element`

#### `ui_lib_group:combo(name, array, def_value?, icon?, tooltip?)`

Creates a combo box element.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Display name. |
| `array` | `string[]` | List of options. |
| `def_value` *(optional)* | `integer` | Default selected index (1-based). |
| `icon` *(optional)* | `string` | Icon identifier. |
| `tooltip` *(optional)* | `string` | Tooltip text. |

**Returns:** `ui_lib_element`

#### `ui_lib_group:multicombo(name, array, def_value?, icon?, tooltip?)`

Creates a multi-combo element.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Display name. |
| `array` | `string[]` | List of options. |
| `def_value` *(optional)* | `any` | Default value. |
| `icon` *(optional)* | `string` | Icon identifier. |
| `tooltip` *(optional)* | `string` | Tooltip text. |

**Returns:** `ui_lib_element`

#### `ui_lib_group:multiselectable(name, array, expand?, icon?, tooltip?)`

Creates a multi-selectable element.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Display name. |
| `array` | `string[]` | List of options. |
| `expand` *(optional)* | `boolean` | Expand by default. |
| `icon` *(optional)* | `string` | Icon identifier. |
| `tooltip` *(optional)* | `string` | Tooltip text. |

**Returns:** `ui_lib_element`

#### `ui_lib_group:button(name, func?, icon?, tooltip?)`

Creates a button element.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Display name. |
| `func` *(optional)* | `function` | Click callback. |
| `icon` *(optional)* | `string` | Icon identifier. |
| `tooltip` *(optional)* | `string` | Tooltip text. |

**Returns:** `ui_lib_element`

#### `ui_lib_group:label(name, icon?, tooltip?)`

Creates a label element.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Display name. |
| `icon` *(optional)* | `string` | Icon identifier. |
| `tooltip` *(optional)* | `string` | Tooltip text. |

**Returns:** `ui_lib_element`

#### `ui_lib_group:colorpicker(name, color, icon?, tooltip?)`

Creates a color picker element.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Display name. |
| `color` | `Color` | Default color. |
| `icon` *(optional)* | `string` | Icon identifier. |
| `tooltip` *(optional)* | `string` | Tooltip text. |

**Returns:** `ui_lib_element`

#### `ui_lib_group:input(name, def_value?, icon?, tooltip?)`

Creates an input box element.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Display name. |
| `def_value` *(optional)* | `string` | Default text. |
| `icon` *(optional)* | `string` | Icon identifier. |
| `tooltip` *(optional)* | `string` | Tooltip text. |

**Returns:** `ui_lib_element`

#### `ui_lib_group:bind(name, def_value?, icon?, tooltip?)`

Creates a key bind element.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Display name. |
| `def_value` *(optional)* | `integer` | Default key code. |
| `icon` *(optional)* | `string` | Icon identifier. |
| `tooltip` *(optional)* | `string` | Tooltip text. |

**Returns:** `ui_lib_element`

#### `ui_lib_group:update()`

Refreshes all element visibility and disable states.

#### `ui_lib_group:set_callback(func, preload?)`

Registers a callback on any element change in this group.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `func` | `function` | Callback function. |
| `preload` *(optional)* | `boolean` | Fire callback immediately. |

**Returns:** `ui_lib_group` — Self for chaining.

#### `ui_lib_group:unset_callback(func)`

Removes a previously registered callback.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `func` | `function` | Callback to remove. |

**Returns:** `ui_lib_group` — Self for chaining.

#### `ui_lib_group:visible_condition(func, set_on?)`

Sets a visibility condition for the entire group.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `func` | `fun(): boolean` | Condition returning true when visible. |
| `set_on` *(optional)* | `boolean` | Apply immediately. |

**Returns:** `ui_lib_group` — Self for chaining.

#### `ui_lib_group:disable_condition(func, set_on?)`

Sets a disable condition for the entire group.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `func` | `fun(): boolean` | Condition returning true when disabled. |
| `set_on` *(optional)* | `boolean` | Apply immediately. |

**Returns:** `ui_lib_group` — Self for chaining.

#### `ui_lib_group:link_to_ui_disable_condition(ui_table)`

Links disable condition to another ui element table.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `ui_table` | `ui_lib_element` | Disable when this element is falsy. |

**Returns:** `ui_lib_group` — Self for chaining.

#### `ui_lib_group:link_to_ui_visible_condition(ui_table)`

Links visibility condition to another ui element table.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `ui_table` | `ui_lib_element` | Show only when this element is truthy. |

**Returns:** `ui_lib_group` — Self for chaining.

## ui_lib_tab

A tab wrapper for organizing groups.

### Methods

#### `ui_lib_tab:create(name, align?)`

Creates a sub-tab or group within this tab.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Display name. |
| `align` *(optional)* | `integer` | Alignment mode. |

**Returns:** `ui_lib_tab|ui_lib_group`

## NEW_UI_LIB

High-level wrapper over the raw menu system.

### Methods

#### `NEW_UI_LIB.create_tab(is_hero)`

Creates menu tabs for hero or generic use.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `is_hero` | `boolean` | True for hero-specific tab. |

**Returns:** `ui_lib_tab|ui_lib_group`

**Overloads:**

- `fun(is_hero: true, name: string, hero_image: string, hero_id: integer): ui_lib_tab|ui_lib_group`
- `fun(is_hero: false, ...: string): ui_lib_tab|ui_lib_group`

#### `NEW_UI_LIB.get_default_group(tab_ref)`

Wraps a raw tab reference into a ui_lib_group.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `tab_ref` | `any` | Raw menu tab reference. |

**Returns:** `ui_lib_group`
