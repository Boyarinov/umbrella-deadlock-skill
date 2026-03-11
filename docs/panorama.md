# Panorama UI

## uipanel

### Methods

#### `uipanel:__tostring()`

Returns a string representation of the panel.

**Returns:** `string`

#### `uipanel:is_valid()`

Checks if the panel pointer is valid and safe to use.

**Returns:** `boolean`

#### `uipanel:get_id()`

Gets the panel's ID.

**Returns:** `string`

#### `uipanel:set_id(id)`

Sets the panel's ID.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `id` | `string` | The new ID. |

#### `uipanel:has_id()`

Checks if the panel has an ID.

**Returns:** `boolean`

#### `uipanel:get_panel_type()`

Gets the panel's type name.

**Returns:** `string`

#### `uipanel:get_parent()`

Gets the panel's parent.

**Returns:** `uipanel` — \| nil

#### `uipanel:find_child(id)`

Finds a direct child by ID.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `id` | `string` | The child's ID. |

**Returns:** `uipanel` — \| nil

#### `uipanel:find_child_traverse(id)`

Finds a child by ID, traversing the entire hierarchy.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `id` | `string` | The child's ID. |

**Returns:** `uipanel` — \| nil

#### `uipanel:find_ancestor(id)`

Finds an ancestor panel by ID.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `id` | `string` | The ancestor's ID. |

**Returns:** `uipanel` — \| nil

#### `uipanel:find_child_in_layout_file(id)`

Finds a child within the panel's layout file by ID.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `id` | `string` | The child's ID. |

**Returns:** `uipanel` — \| nil

#### `uipanel:find_children_with_class_traverse(class_name)`

Finds all children (recursive) that have a specific class.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `class_name` | `string` | The class name to search for. |

**Returns:** `uipanel[].`

#### `uipanel:children()`

Gets a list of direct children.

**Returns:** `uipanel[]`

#### `uipanel:get_child_count()`

Gets the number of direct children.

**Returns:** `integer`

#### `uipanel:get_child(index)`

Gets a direct child by its index.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `index` | `integer` | The child index (0-based). |

**Returns:** `uipanel` — \| nil

#### `uipanel:get_first_child()`

Gets the first direct child.

**Returns:** `uipanel` — \| nil

#### `uipanel:get_last_child()`

Gets the last direct child.

**Returns:** `uipanel` — \| nil

#### `uipanel:get_child_index(child)`

Gets the index of a direct child panel.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `child` | `uipanel` | The child panel. |

**Returns:** `integer`

#### `uipanel:get_actual_layout_width()`

Gets the actual width of the panel after being positioned by other panels.

**Returns:** `number`

#### `uipanel:get_actual_layout_height()`

Gets the actual height of the panel after being positioned by other panels.

**Returns:** `number`

#### `uipanel:set_visible(visible)`

Sets the panel's visibility.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `visible` | `boolean` | True to make visible, false to hide. |

#### `uipanel:is_visible()`

Checks if the panel is visible.

**Returns:** `boolean`

#### `uipanel:get_class_list()`

Gets a list of all classes on the panel.

**Returns:** `string[]`

#### `uipanel:add_class(class_name)`

Adds a single class to the panel.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `class_name` | `string` | The class to add. |

#### `uipanel:remove_class(class_name)`

Removes a single class from the panel.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `class_name` | `string` | The class to remove. |

#### `uipanel:add_classes(class_names)`

Adds multiple classes from a space-separated string.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `class_names` | `string` | A space-separated list of classes. |

#### `uipanel:remove_classes(class_names)`

Removes multiple classes from a space-separated string.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `class_names` | `string` | A space-separated list of classes. |

#### `uipanel:has_class(class_name)`

Checks if the panel has a specific class.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `class_name` | `string` | The class to check for. |

**Returns:** `boolean`

#### `uipanel:ascendant_has_class(class_name)`

Checks if the panel or any ancestor has a specific class.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `class_name` | `string` | The class to check for. |

**Returns:** `boolean`

#### `uipanel:set_has_class(class_name, add)`

Adds or removes a class based on a boolean.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `class_name` | `string` | The class to add or remove. |
| `add` | `boolean` | True to add, false to remove. |

#### `uipanel:trigger_class(class_name)`

Removes and immediately re-adds a class. Useful for re-triggering animations or sound effects.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `class_name` | `string` | The class to trigger. |

#### `uipanel:set_draggable(draggable)`

Sets whether the panel can be dragged.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `draggable` | `boolean` | True to make draggable. |

#### `uipanel:is_draggable()`

Checks if the panel is draggable.

**Returns:** `boolean`

#### `uipanel:get_attribute_string(name)`

Gets a string attribute from the panel.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | The name of the attribute. |

**Returns:** `string`

#### `uipanel:set_attribute_string(name, value)`

Sets a string attribute on the panel.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | The name of the attribute. |
| `value` | `string` | The value to set. |

#### `uipanel:set_style(style_string)`

Applies a string of CSS-like styles to the panel.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `style_string` | `string` | The styles to apply (e.g., "width: 100px; height: 100px;"). |

**Returns:** `boolean`

#### `uipanel:apply_styles(force_reflow?)`

Forces the panel to re-apply its styles.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `force_reflow` *(optional)* | `boolean` |  |

#### `uipanel:remove_and_delete_children()`

Removes all children and deletes them.

#### `uipanel:get_text()`

Gets the text of the label panel.

**Returns:** `string`

#### `uipanel:set_text(text)`

Sets the text of the label panel.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `text` | `string` | The text to set. |

#### `uipanel:get_image_src()`

Gets the image source of the image panel. (EconItemImage, Image, CitadelHeroImage)

**Returns:** `string`

#### `uipanel:get_screen_position()`

Gets the panel's absolute position on the screen.

**Returns:** `Vec2`

#### `uipanel:get_bounds()`

Gets the panel's layout bounds (x, y, width, height).

**Returns:** `Vec2` — position, `Vec2` — size

#### `uipanel:run_script(script_code)`

Runs a JavaScript snippet in the context of this panel.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `script_code` | `string` | The JavaScript code to execute. |

#### `uipanel:find_child_by_path(path, with_logs?)`

Finds a child by a path of child IDs starting from this panel.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `path` | `string[]` | An array-like table of child IDs representing the path. |
| `with_logs` *(optional)* | `boolean` | Whether to log errors if not found. |

**Returns:** `uipanel` — \| nil

#### `uipanel:find_child_with_class(class_name)`

Finds the first direct child that has a specific class.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `class_name` | `string` | The class name to search for. |

**Returns:** `uipanel` — \| nil

#### `uipanel:find_children_with_id_traverse(id_name)`

Finds all children (recursive) that have a specific ID.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `id_name` | `string` | The ID to search for. |

**Returns:** `uipanel[]`

#### `uipanel:switch_class(category_name, class_name)`

Switches a class within a category. Removes all classes in the category and adds the specified class.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `category_name` | `string` | The category name. |
| `class_name` | `string` | The class to add. |

#### `uipanel:delete_async(delay)`

Delete a panel

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `delay` | `number` | delay before delete |

#### `uipanel:load_layout_file(file_path, override_existed)`

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `file_path` | `string` | The path to the layout file to load (e.g., "file://{resources}/layout/custom_layout.xml"). |
| `override_existed` | `boolean` | True to override the existing layout, false to keep it. |

## panorama

### Methods

#### `panorama.get_panel_by_id(id)`

Finds a panel by its ID.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `id` | `string` | The ID of the panel to find. |

**Returns:** `uipanel` — \| nil

#### `panorama.get_panel_by_panel_type(type)`

Finds the first panel of a given panel type name.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `type` | `string` | The panel type name. (e.g., "Panel", "Label"). |

**Returns:** `uipanel` — \| nil

#### `panorama.get_panel_by_path(path, log_error?)`

Finds a panel by a path of child IDs.
First element get_panel_by_id then find_child for each subsequent element.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `path` | `string[]` | An array-like table of child IDs representing the path. |
| `log_error` *(optional)* | `boolean` | Whether to log an error if not found. |

**Returns:** `uipanel` — \| nil

#### `panorama.create_panel(type, id, parent, classes?, styles?)`

Creates a new panel and attaches it to a parent.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `type` | `string` | The panel type to create (e.g., "Panel", "Label"). |
| `id` | `string` | The ID for the new panel. |
| `parent` | `uipanel` | The parent panel. |
| `classes` *(optional)* | `string` | A space-separated list of classes to add. |
| `styles` *(optional)* | `string` | A string of CSS-like styles to apply. |

**Returns:** `uipanel` — \| nil

#### `panorama.sym2string(sym)`

Converts a raw Panorama symbol integer to its string representation.
WARNING: Invalid symbol IDs may crash. No nil-safety path.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `sym` | `integer` | Raw Panorama symbol ID. |

**Returns:** `string`

## file_spoofer

### Methods

#### `file_spoofer.add_resource(file_path, content)`

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `file_path` | `string` | The path to the resource file to spoof/add (e.g., "panorama/styles/popups/popup_settings_old.vcss_c"). |
| `content` | `string` | The content to use for the spoofed resource. |

**Returns:** `boolean` — true if the resource was added successfully, false otherwise.

#### `file_spoofer.reload_resource(file_path)`

Trigger a reload of a resource file.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `file_path` | `string` | The path to the resource file to reload (e.g., "panorama/styles/popups/popup_settings_old.vcss_c"). |

#### `file_spoofer.add_folder(dir_path)`

Spoof whole directory by adding all files from it to the resource system

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `dir_path` | `string` |  |
