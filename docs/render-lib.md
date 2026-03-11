# Render Library

## LIB_RENDER

Render library wrapping the raw Render API with caching, animations, and a hitbox/button system.

### Fields

| Name | Type | Description |
|------|------|-------------|
| `loaded_fonts` | `table<string, integer>` | Cached loaded fonts by name. |
| `loaded_images` | `table<string, integer>` | Cached loaded images by path. |
| `screen_size` | `Vec2` | Current screen size. |
| `anim_values` | `table<string, number>` | Named animation state values. |
| `anim_value` | `number` | Frame-scaled animation delta. |
| `hitbox_array` | `table` | Registered hitbox elements. |
| `block_deadlock` | `table` | Input blocking registry. |
| `drag_activate_distance` | `number` | Default drag activation distance (5). |
| `drag_activate_hold_time` | `number` | Default drag hold time (0.12). |
| `debug_button` | `boolean` | Enable button hitbox debug rendering. |
| `debug_drag` | `boolean` | Enable drag hitbox debug rendering. |
| `cursos_pos` | `Vector` | Current cursor position. |
| `easings` | `{out_quart: (fun(value: number): number), in_quart: (fun(value: number): number), in_out_quart: (fun(value: number): number), in_out_cubic: (fun(value: number): number)}` | Easing functions. |

### Methods

#### `LIB_RENDER.font(name, fontflag?, weight?)`

Loads or retrieves a cached font by name.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Font name. |
| `fontflag` *(optional)* | `string\|string[]` | Font creation flags from Enum.FontCreate. |
| `weight` *(optional)* | `number` | Font weight. |

**Returns:** `integer` — Font handle.

#### `LIB_RENDER.load_image(path, filter?)`

Loads or retrieves a cached image by path.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `path` | `string` | Image file path. |
| `filter` *(optional)* | `string` | Image filter mode. |

**Returns:** `integer` — Image handle.

#### `LIB_RENDER.centered_notification(text, duration)`

Displays a centered on-screen notification.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `text` | `string` | Notification text. |
| `duration` | `number` | Display duration in seconds. |

#### `LIB_RENDER.is_visible(position, size?, is_centered?)`

Returns whether a position (and optional area) is visible on screen.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `position` | `Vec2` | Screen position. |
| `size` *(optional)* | `Vec2` | Area size. |
| `is_centered` *(optional)* | `boolean` | Whether position is the center of the area. |

**Returns:** `boolean` — True if visible.

#### `LIB_RENDER.in_bounds(pos_1, pos_2)`

Returns true if the cursor is within the rectangular bounds.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pos_1` | `Vec2` | Top-left corner. |
| `pos_2` | `Vec2` | Bottom-right corner. |

**Returns:** `boolean` — True if cursor is inside bounds.

#### `LIB_RENDER.line(pos_1, pos_2, color, thickness?)`

Draws a line between two points.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pos_1` | `Vector\|Vec2` | Start position. |
| `pos_2` | `Vector\|Vec2` | End position. |
| `color` | `Color` | Line color. |
| `thickness` *(optional)* | `number` | Line thickness. |

#### `LIB_RENDER.line_arrowed(start, end_, line_color, arrow_color, arrows_count?, arrow_size?, line_thickness?, arrow_thickness?)`

Draws a line with arrow marker(s) along it.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `start` | `Vector\|Vec2` | Start position. |
| `end_` | `Vector\|Vec2` | End position. |
| `line_color` | `Color` | Line color. |
| `arrow_color` | `Color` | Arrow color. |
| `arrows_count` *(optional)* | `integer` | Number of arrows. |
| `arrow_size` *(optional)* | `number` | Arrow head size. |
| `line_thickness` *(optional)* | `number` | Line thickness. |
| `arrow_thickness` *(optional)* | `number` | Arrow line thickness. |

#### `LIB_RENDER.filled_rect(pos_1, pos_2, color, round?, flags?)`

Draws a filled rectangle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pos_1` | `Vector\|Vec2` | Top-left corner. |
| `pos_2` | `Vector\|Vec2` | Bottom-right corner. |
| `color` | `Color` | Fill color. |
| `round` *(optional)* | `number` | Corner rounding radius. |
| `flags` *(optional)* | `Enum.DrawFlags` | Draw flags. |

#### `LIB_RENDER.outline_rect(pos_1, pos_2, color, round?, flags?, thickness?)`

Draws an outlined rectangle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pos_1` | `Vector\|Vec2` | Top-left corner. |
| `pos_2` | `Vector\|Vec2` | Bottom-right corner. |
| `color` | `Color` | Outline color. |
| `round` *(optional)* | `number` | Corner rounding radius. |
| `flags` *(optional)* | `Enum.DrawFlags` | Draw flags. |
| `thickness` *(optional)* | `number` | Outline thickness. |

#### `LIB_RENDER.gradient(pos_1, pos_2, lup_color, rup_color, ldown_color, rdown_color, round?, flags?)`

Draws a gradient-filled rectangle with per-corner colors.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pos_1` | `Vector\|Vec2` | Top-left corner. |
| `pos_2` | `Vector\|Vec2` | Bottom-right corner. |
| `lup_color` | `Color` | Left-upper color. |
| `rup_color` | `Color` | Right-upper color. |
| `ldown_color` | `Color` | Left-lower color. |
| `rdown_color` | `Color` | Right-lower color. |
| `round` *(optional)* | `number` | Corner rounding radius. |
| `flags` *(optional)* | `Enum.DrawFlags` | Draw flags. |

#### `LIB_RENDER.glow(pos_1, pos_2, color, thickness, round?, flags?, offset?)`

Draws a glow effect around a rectangle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pos_1` | `Vector\|Vec2` | Top-left corner. |
| `pos_2` | `Vector\|Vec2` | Bottom-right corner. |
| `color` | `Color` | Glow color. |
| `thickness` | `number` | Glow thickness. |
| `round` *(optional)* | `number` | Corner rounding radius. |
| `flags` *(optional)* | `Enum.DrawFlags` | Draw flags. |
| `offset` *(optional)* | `Vec2` | Glow offset. |

#### `LIB_RENDER.blur(pos_1, pos_2, strength, round?, alpha?, flags?)`

Draws a blurred rectangle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pos_1` | `Vector\|Vec2` | Top-left corner. |
| `pos_2` | `Vector\|Vec2` | Bottom-right corner. |
| `strength` | `number` | Blur strength. |
| `round` *(optional)* | `number` | Corner rounding radius. |
| `alpha` *(optional)* | `number` | Blur alpha (0.0-1.0). |
| `flags` *(optional)* | `Enum.DrawFlags` | Draw flags. |

#### `LIB_RENDER.triagle(points, color)`

Draws an outlined triangle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `points` | `Vec2[]` | Three triangle vertices. |
| `color` | `Color` | Outline color. |

#### `LIB_RENDER.filled_triagle(points, color)`

Draws a filled triangle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `points` | `Vec2[]` | Three triangle vertices. |
| `color` | `Color` | Fill color. |

#### `LIB_RENDER.circle(pos, radius, color, thickness?, start_deg?, fill_range?, round_corners?, segments?)`

Draws an outlined circle or arc.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pos` | `Vector\|Vec2` | Center position. |
| `radius` | `number` | Circle radius. |
| `color` | `Color` | Outline color. |
| `thickness` *(optional)* | `number` | Outline thickness. |
| `start_deg` *(optional)* | `number` | Start angle in degrees. |
| `fill_range` *(optional)* | `number` | Arc fill range in degrees. |
| `round_corners` *(optional)* | `boolean` | Round the arc endpoints. |
| `segments` *(optional)* | `integer` | Number of segments. |

#### `LIB_RENDER.filled_circle(pos, radius, color, start_deg?, fill_range?, segments?)`

Draws a filled circle or arc.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pos` | `Vector\|Vec2` | Center position. |
| `radius` | `number` | Circle radius. |
| `color` | `Color` | Fill color. |
| `start_deg` *(optional)* | `number` | Start angle in degrees. |
| `fill_range` *(optional)* | `number` | Arc fill range in degrees. |
| `segments` *(optional)* | `integer` | Number of segments. |

#### `LIB_RENDER.gradient_circle(pos, radius, outline_color, inline_color, start_deg?, fill_range?)`

Draws a gradient circle with distinct outline and inline colors.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pos` | `Vector\|Vec2` | Center position. |
| `radius` | `number` | Circle radius. |
| `outline_color` | `Color` | Outer color. |
| `inline_color` | `Color` | Inner color. |
| `start_deg` *(optional)* | `number` | Start angle in degrees. |
| `fill_range` *(optional)* | `number` | Arc fill range in degrees. |

#### `LIB_RENDER.glow_circle(pos, radius, color, thickness, segments?, flags?, offset?)`

Draws a glow effect around a circle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pos` | `Vector\|Vec2` | Center position. |
| `radius` | `number` | Circle radius. |
| `color` | `Color` | Glow color. |
| `thickness` | `number` | Glow thickness. |
| `segments` *(optional)* | `integer` | Number of segments. |
| `flags` *(optional)* | `Enum.DrawFlags` | Draw flags. |
| `offset` *(optional)* | `Vec2` | Glow offset. |

#### `LIB_RENDER.clip(pos_1, pos_2, intersect?)`

Pushes a clip rectangle onto the clip stack.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pos_1` | `Vector\|Vec2` | Top-left corner. |
| `pos_2` | `Vector\|Vec2` | Bottom-right corner. |
| `intersect` *(optional)* | `boolean` | Intersect with existing clip rect. |

#### `LIB_RENDER.pop_clip()`

Pops the last clip rectangle from the clip stack.

#### `LIB_RENDER.image(path, pos, size, centered, color, round?, corner_flags?, cut_min?, cut_max?, gray_scale?, filter?)`

Renders a cached image with optional transformations.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `path` | `string` | Image file path. |
| `pos` | `Vector\|Vec2` | Draw position. |
| `size` | `Vec2\|number` | Image size (Vec2 for width/height, number for uniform). |
| `centered` | `boolean` | Whether position is the center. |
| `color` | `Color` | Tint color. |
| `round` *(optional)* | `number` | Corner rounding radius. |
| `corner_flags` *(optional)* | `Enum.DrawFlags` | Corner flags. |
| `cut_min` *(optional)* | `Vec2` | UV minimum cut. |
| `cut_max` *(optional)* | `Vec2` | UV maximum cut. |
| `gray_scale` *(optional)* | `number` | Grayscale amount (0.0-1.0). |
| `filter` *(optional)* | `string` | Image filter mode. |

#### `LIB_RENDER.text_size(font_name, size, text, dont_cache?)`

Returns the rendered size of a text string.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `font_name` | `string\|integer\|nil` | Font name, handle, or nil for default. |
| `size` | `number` | Font size. |
| `text` | `string` | Text to measure. |
| `dont_cache` *(optional)* | `boolean` | Skip font cache lookup. |

**Returns:** `Vec2` — Text dimensions.

#### `LIB_RENDER.text(font_name, size, pos, text, color, center_array?, shadow_offset_array?, dont_cache?)`

Draws text at a position with optional centering and shadow.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `font_name` | `string\|integer\|nil` | Font name, handle, or nil for default. |
| `size` | `number` | Font size. |
| `pos` | `Vector\|Vec2` | Draw position. |
| `text` | `string` | Text to draw. |
| `color` | `Color` | Text color. |
| `center_array` *(optional)* | `{[1]: boolean, [2]: boolean}` | Horizontal and vertical centering. |
| `shadow_offset_array` *(optional)* | `{x: integer, y: integer}` | Shadow offset. |
| `dont_cache` *(optional)* | `boolean` | Skip font cache lookup. |

#### `LIB_RENDER.clone(vector)`

Clones a Vector or Vec2 into a new Vector.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `vector` | `Vector\|Vec2` | Source vector. |

**Returns:** `Vector` — Cloned vector.

#### `LIB_RENDER.clone_c(orig_color, a?, r?, g?, b?, disable_mult?)`

Clones a color with optional channel overrides.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `orig_color` | `Color` | Source color. |
| `a` *(optional)* | `number` | Alpha channel value. |
| `r` *(optional)* | `number` | Red channel value. |
| `g` *(optional)* | `number` | Green channel value. |
| `b` *(optional)* | `number` | Blue channel value. |
| `disable_mult` *(optional)* | `boolean` | When true values replace channels; when false (default) values multiply. |

**Returns:** `Color` — New color.

#### `LIB_RENDER.theme(name)`

Returns a menu theme color by name.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `name` | `string` | Theme color name. |

**Returns:** `Color` — Theme color.

#### `LIB_RENDER.localizer(token)`

Localizes a token string, auto-registering it if needed.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `token` | `string` | Localization token. |

**Returns:** `string` — Localized string.

#### `LIB_RENDER.calculate_value(var_name, state, mult?, min?, max?)`

Smoothly interpolates a named value toward 0 or 1 based on state, clamped.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `var_name` | `string` | Animation variable name. |
| `state` | `boolean` | Target state (true = 1, false = 0). |
| `mult` *(optional)* | `number` | Animation speed multiplier. |
| `min` *(optional)* | `number` | Minimum output value. |
| `max` *(optional)* | `number` | Maximum output value. |

**Returns:** `number` — Current interpolated value.

#### `LIB_RENDER.calculate_value_no_clamp(var_name, state, mult?, min?, max?)`

Smoothly interpolates a named value toward 0 or 1, allowing overshoot before easing back.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `var_name` | `string` | Animation variable name. |
| `state` | `boolean` | Target state (true = 1, false = 0). |
| `mult` *(optional)* | `number` | Animation speed multiplier. |
| `min` *(optional)* | `number` | Minimum output value. |
| `max` *(optional)* | `number` | Maximum output value. |

**Returns:** `number` — Current interpolated value (may exceed min/max during transition).

#### `LIB_RENDER.drag_hitbox(pos_1, pos_2, func?, key_code?, enable_deadlock_input?, dont_edit_pos?)`

Creates a drag hitbox for tracking drag gestures within a region.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pos_1` | `Vector\|Vec2` | Top-left corner. |
| `pos_2` | `Vector\|Vec2` | Bottom-right corner. |
| `func` *(optional)* | `fun()` | Callback on drag. |
| `key_code` *(optional)* | `Enum.ButtonCode` | Activation key code. |
| `enable_deadlock_input` *(optional)* | `boolean` | Block game input while dragging. |
| `dont_edit_pos` *(optional)* | `boolean` | Prevent automatic position updates. |

**Returns:** `lib_render_drag_hitbox` — Drag hitbox instance.

#### `LIB_RENDER.button_hitbox(pos_1, pos_2, def_value?, key_code?, func?, enable_deadlock_input?, dont_block_other?, custom_func_call_logic?)`

Creates a button hitbox for tracking click interactions within a region.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pos_1` | `Vector\|Vec2` | Top-left corner. |
| `pos_2` | `Vector\|Vec2` | Bottom-right corner. |
| `def_value` *(optional)* | `boolean\|nil` | Default button value. |
| `key_code` *(optional)* | `Enum.ButtonCode` | Activation key code. |
| `func` *(optional)* | `fun()` | Callback on click. |
| `enable_deadlock_input` *(optional)* | `boolean` | Block game input while interacting. |
| `dont_block_other` *(optional)* | `boolean` | Allow other hitboxes to receive input simultaneously. |
| `custom_func_call_logic` *(optional)* | `boolean` | Use custom callback invocation logic. |

**Returns:** `lib_render_button_hitbox` — Button hitbox instance.

## lib_render_drag_hitbox

Drag hitbox returned by LIB_RENDER.drag_hitbox.

### Fields

| Name | Type | Description |
|------|------|-------------|
| `pos_1` | `Vector\|Vec2` | Top-left position. |
| `pos_2` | `Vector\|Vec2` | Bottom-right position. |
| `is_active` | `boolean` | Whether the drag is currently active. |
| `was_dragged` | `boolean` | Whether the hitbox was dragged this frame. |

### Methods

#### `lib_render_drag_hitbox:disable_condition(func)`

Sets a condition function that disables the hitbox when it returns true.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `func` | `fun(): boolean` | Disable condition callback. |

**Returns:** `lib_render_drag_hitbox` — Self for chaining.

#### `lib_render_drag_hitbox:override_key_code(key_code)`

Overrides the key code used to activate the drag.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `key_code` | `Enum.ButtonCode` | Key code override. |

**Returns:** `lib_render_drag_hitbox` — Self for chaining.

#### `lib_render_drag_hitbox:set_drag_activation(distance?, hold_time?)`

Sets both drag activation distance and hold time.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `distance` *(optional)* | `number` | Activation distance threshold. |
| `hold_time` *(optional)* | `number` | Hold time threshold in seconds. |

**Returns:** `lib_render_drag_hitbox` — Self for chaining.

#### `lib_render_drag_hitbox:set_drag_distance(distance)`

Sets the drag activation distance.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `distance` | `number` | Activation distance threshold. |

**Returns:** `lib_render_drag_hitbox` — Self for chaining.

#### `lib_render_drag_hitbox:set_drag_hold_time(hold_time)`

Sets the drag hold time.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `hold_time` | `number` | Hold time threshold in seconds. |

**Returns:** `lib_render_drag_hitbox` — Self for chaining.

## lib_render_button_hitbox

Button hitbox returned by LIB_RENDER.button_hitbox.

### Fields

| Name | Type | Description |
|------|------|-------------|
| `pos_1` | `Vector\|Vec2` | Top-left position. |
| `pos_2` | `Vector\|Vec2` | Bottom-right position. |
| `value` | `boolean\|nil` | Current button value. |
| `last_usage_time` | `number` | Timestamp of last interaction. |
| `hold_time` | `number` | Duration the button has been held. |
| `move_distance` | `number` | Distance cursor moved since press. |
| `moved_from_press` | `boolean` | Whether cursor moved from the press origin. |
| `hold_reached` | `boolean` | Whether hold time threshold was reached. |

### Methods

#### `lib_render_button_hitbox:disable_condition(func)`

Sets a condition function that disables the hitbox when it returns true.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `func` | `fun(): boolean` | Disable condition callback. |

**Returns:** `lib_render_button_hitbox` — Self for chaining.

#### `lib_render_button_hitbox:override_key_code(key_code)`

Overrides the key code used to activate the button.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `key_code` | `Enum.ButtonCode` | Key code override. |

**Returns:** `lib_render_button_hitbox` — Self for chaining.

#### `lib_render_button_hitbox:set_drag_activation(distance?, hold_time?)`

Sets both drag activation distance and hold time.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `distance` *(optional)* | `number` | Activation distance threshold. |
| `hold_time` *(optional)* | `number` | Hold time threshold in seconds. |

**Returns:** `lib_render_button_hitbox` — Self for chaining.

#### `lib_render_button_hitbox:set_drag_distance(distance)`

Sets the drag activation distance.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `distance` | `number` | Activation distance threshold. |

**Returns:** `lib_render_button_hitbox` — Self for chaining.

#### `lib_render_button_hitbox:set_drag_hold_time(hold_time)`

Sets the drag hold time.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `hold_time` | `number` | Hold time threshold in seconds. |

**Returns:** `lib_render_button_hitbox` — Self for chaining.

#### `lib_render_button_hitbox:delete()`

Deletes the button hitbox, removing it from the hitbox array.
