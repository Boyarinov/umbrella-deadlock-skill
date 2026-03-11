# Rendering

### `Render.FilledRect(start, end_, color, rounding?, flags?)`

Draws a filled rectangle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `start` | `Vec2` | The starting point of the rectangle. |
| `end_` | `Vec2` | The ending point of the rectangle. |
| `color` | `Color` | The color of the rectangle. |
| `rounding` *(optional)* | `number` | Default: `0.0`. The rounding radius of the rectangle corners. |
| `flags` *(optional)* | `Enum.DrawFlags` | Default: `Enum.DrawFlags.None`. Custom flags for drawing. |

**Returns:** `nil`

### `Render.Rect(start, end_, color, rounding?, flags?, thickness?)`

Draws an unfilled rectangle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `start` | `Vec2` | The starting point of the rectangle. |
| `end_` | `Vec2` | The ending point of the rectangle. |
| `color` | `Color` | The color of the rectangle's border. |
| `rounding` *(optional)* | `number` | Default: `0.0`. The rounding radius of the rectangle corners. |
| `flags` *(optional)* | `Enum.DrawFlags` | Default: `Enum.DrawFlags.None`. Custom flags for drawing. |
| `thickness` *(optional)* | `number` | Default: `1.0`. The thickness of the rectangle's border. |

**Returns:** `nil`

### `Render.RoundedProgressRect(start, end_, color, percent, rounding, thickness?)`

Draw a progress rectangle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `start` | `Vec2` | The starting point of the rectangle. |
| `end_` | `Vec2` | The ending point of the rectangle. |
| `color` | `Color` | The color of the rectangle. |
| `percent` | `number` | The percentage of the rectangle to fill [0..1]. |
| `rounding` | `number` | The rounding radius of the rectangle corners. |
| `thickness` *(optional)* | `number` | Default: `1.0`. The thickness of the rectangle's border. |

**Returns:** `nil`

### `Render.Line(start, end_, color, thickness?)`

Draws a line between two points.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `start` | `Vec2` | The starting point of the line. |
| `end_` | `Vec2` | The ending point of the line. |
| `color` | `Color` | The color of the line. |
| `thickness` *(optional)* | `number` | Default: `1.0`. The thickness of the line. |

**Returns:** `nil`

### `Render.PolyLine(points, color, thickness?)`

Draws a series of connected lines (polyline).

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `points` | `Vec2[]` | A table of Vec2 points to connect with lines. |
| `color` | `Color` | The color of the polyline. |
| `thickness` *(optional)* | `number` | Default: `1.0`. The thickness of the polyline. |

**Returns:** `nil`

### `Render.Circle(pos, radius, color, thickness?, startDeg?, percentage?, rounded?, segments?)`

Draws a circle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pos` | `Vec2` | The center position of the circle. |
| `radius` | `number` | The radius of the circle. |
| `color` | `Color` | The color of the circle. |
| `thickness` *(optional)* | `number` | Default: `1.0`. The thickness of the circle's outline. |
| `startDeg` *(optional)* | `number` | Default: `0.0`. The starting degree for drawing the circle. 0 is right side, 90 is bottom, 180 is left, 270 is top. |
| `percentage` *(optional)* | `number` | Default: `1.0`. The percentage of the circle to draw, in the range [0.0-1.0]. |
| `rounded` *(optional)* | `boolean` | Default: `false`. Whether the circle is rounded. |
| `segments` *(optional)* | `integer` | Default: `32`. The number of segments used for drawing the circle. |

**Returns:** `nil`

### `Render.FilledCircle(pos, radius, color, startDeg?, percentage?, segments?)`

Draws a filled circle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pos` | `Vec2` | The center position of the circle. |
| `radius` | `number` | The radius of the circle. |
| `color` | `Color` | The color of the circle. |
| `startDeg` *(optional)* | `number` | Default: `0.0`. The starting degree for drawing the circle. 0 is right side, 90 is bottom, 180 is left, 270 is top. |
| `percentage` *(optional)* | `number` | Default: `1.0`. The percentage of the circle to draw, in the range [0.0-1.0]. |
| `segments` *(optional)* | `integer` | Default: `32`. The number of segments used for drawing the circle. |

**Returns:** `nil`

### `Render.CircleGradient(pos, radius, colorOuter, colorInner, startDeg?, percentage?)`

Draws a circle with a gradient.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pos` | `Vec2` | The center position of the circle. |
| `radius` | `number` | The radius of the circle. |
| `colorOuter` | `Color` | The outer color of the gradient. |
| `colorInner` | `Color` | The inner color of the gradient. |
| `startDeg` *(optional)* | `number` | Default: `0.0`. The starting degree for drawing the circle. 0 is right side, 90 is bottom, 180 is left, 270 is top. |
| `percentage` *(optional)* | `number` | Default: `1.0`. The percentage of the circle to draw, in the range [0.0-1.0]. |

**Returns:** `nil`

### `Render.Triangle(points, color, thickness?)`

Draws a triangle outline.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `points` | `Vec2[]` | A table of three Vec2 points defining the vertices of the triangle. |
| `color` | `Color` | The color of the triangle's outline. |
| `thickness` *(optional)* | `number` | Default: `1.0`. The thickness of the triangle's outline. |

**Returns:** `nil`

### `Render.FilledTriangle(points, color)`

Draws a filled triangle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `points` | `Vec2[]` | A table of three Vec2 points defining the vertices of the triangle. |
| `color` | `Color` | The color of the triangle. |

**Returns:** `nil`

### `Render.TexturedPoly(points, textureHandle, color, grayscale?)`

Draws a textured polygon.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `points` | `Vertex[]` | A table of Vertex points defining the vertices of the polygon. Each Vertex contains a position (Vec2) and a texture coordinate (Vec2). |
| `textureHandle` | `integer` | The handle to the texture to be applied to the polygon. |
| `color` | `Color` | The color to apply over the texture. This can be used to tint the texture. |
| `grayscale` *(optional)* | `number` | Default: `0.0`. The grayscale of the image. |

**Returns:** `nil`

### `Render.LoadFont(fontName, fontFlag?, weight?)`

Loads a font and returns its handle. Returns handle to the loaded font.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `fontName` | `string` | The name of the font to load. |
| `fontFlag` *(optional)* | `Enum.FontCreate\|integer` | Default: `Enum.FontCreate.FONTFLAG_NONE`. Flags for font creation, such as antialiasing. |
| `weight` *(optional)* | `integer` | Default: `400`. The weight (thickness) of the font. Typically, 0 means default weight. |

**Returns:** `integer`

### `Render.Text(font, fontSize, text, pos, color)`

Draws text at a specified position.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `font` | `integer` | The handle to the font used for drawing the text. |
| `fontSize` | `number` | The size of the font. |
| `text` | `string` | The text to be drawn. |
| `pos` | `Vec2` | The position where the text will be drawn. |
| `color` | `Color` | The color of the text. |

**Returns:** `nil`

### `Render.WorldToScreen(pos)`

Converts a 3D world position to a 2D screen position. Returns A Vec2 representing the 2D screen position and a boolean indicating visibility on the screen.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pos` | `Vector` | The 3D world position to be converted. |

**Returns:** `Vec2` — screenPos, `boolean` — isVisible

### `Render.ScreenSize()`

Retrieves the current screen size, returning it as a Vec2 where x is the width and y is the height of the screen.

**Returns:** `Vec2`

### `Render.TextSize(font, fontSize, text)`

Calculates the size of the given text using the specified font, returning the size as a Vec2 where x is the width and y is the height of the text.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `font` | `integer` | The handle to the font used for measuring the text. |
| `fontSize` | `number` | The size of the font. |
| `text` | `string` | The text to measure. |

**Returns:** `Vec2`

### `Render.LoadImage(path, filter?)`

Loads an image and returns its handle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `path` | `string` | Path to the image. |
| `filter` *(optional)* | `Enum.ImageFilter` |  |

**Returns:** `integer`

### `Render.Image(imageHandle, pos, size, color, rounding?, flags?, uvMin?, uvMax?, grayscale?)`

Draws an image at a specified position and size.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `imageHandle` | `integer` | The handle to the image. |
| `pos` | `Vec2` | The position to draw the image. |
| `size` | `Vec2` | The size of the image. |
| `color` | `Color` | The color to tint the image. |
| `rounding` *(optional)* | `number` | Default: `0.0`. The rounding radius of the image corners. |
| `flags` *(optional)* | `Enum.DrawFlags` | Default: `Enum.DrawFlags.None`. Custom flags for drawing. |
| `uvMin` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. The minimum UV coordinates for texture mapping. |
| `uvMax` *(optional)* | `Vec2` | Default: `{1.0, 1.0}`. The maximum UV coordinates for texture mapping. |
| `grayscale` *(optional)* | `number` | Default: `0.0`. The grayscale of the image. |

**Returns:** `nil`

### `Render.ImageCentered(imageHandle, pos, size, color, rounding?, flags?, uvMin?, uvMax?, grayscale?)`

Draws an image centered at a specified position and size.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `imageHandle` | `integer` | The handle to the image. |
| `pos` | `Vec2` | The center position to draw the image. |
| `size` | `Vec2` | The size of the image. |
| `color` | `Color` | The color to tint the image. |
| `rounding` *(optional)* | `number` | Default: `0.0`. The rounding radius of the image corners. |
| `flags` *(optional)* | `Enum.DrawFlags` | Default: `Enum.DrawFlags.None`. Custom flags for drawing. |
| `uvMin` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. The minimum UV coordinates for texture mapping. |
| `uvMax` *(optional)* | `Vec2` | Default: `{1.0, 1.0}`. The maximum UV coordinates for texture mapping. |
| `grayscale` *(optional)* | `number` | Default: `0.0`. The grayscale of the image. |

**Returns:** `nil`

### `Render.ImageSize(imageHandle)`

Retrieves the size of an image. Returns the size of the image as a Vec2.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `imageHandle` | `integer` | The handle to the image. |

**Returns:** `Vec2`

### `Render.OutlineGradient(start, end_, topLeft, topRight, bottomLeft, bottomRight, rounding?, flags?, thickness?)`

Draws a outlined gradient rectangle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `start` | `Vec2` | The starting point of the gradient rectangle. |
| `end_` | `Vec2` | The ending point of the gradient rectangle. |
| `topLeft` | `Color` | The color of the top-left corner. |
| `topRight` | `Color` | The color of the top-right corner. |
| `bottomLeft` | `Color` | The color of the bottom-left corner. |
| `bottomRight` | `Color` | The color of the bottom-right corner. |
| `rounding` *(optional)* | `number` | Default: `0.0`. The rounding radius of the rectangle corners. |
| `flags` *(optional)* | `Enum.DrawFlags` | Default: `Enum.DrawFlags.None`. Custom flags for drawing. |
| `thickness` *(optional)* | `number` | Default: `1.0`. The thickness of the outline. |

**Returns:** `nil`

### `Render.Gradient(start, end_, topLeft, topRight, bottomLeft, bottomRight, rounding?, flags?)`

Draws a filled gradient rectangle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `start` | `Vec2` | The starting point of the gradient rectangle. |
| `end_` | `Vec2` | The ending point of the gradient rectangle. |
| `topLeft` | `Color` | The color of the top-left corner. |
| `topRight` | `Color` | The color of the top-right corner. |
| `bottomLeft` | `Color` | The color of the bottom-left corner. |
| `bottomRight` | `Color` | The color of the bottom-right corner. |
| `rounding` *(optional)* | `number` | Default: `0.0`. The rounding radius of the rectangle corners. |
| `flags` *(optional)* | `Enum.DrawFlags` | Default: `Enum.DrawFlags.None`. Custom flags for drawing. |

**Returns:** `nil`

### `Render.Shadow(start, end_, color, thickness, obj_rounding?, flags?, offset?)`

Draws a shadow effect within a specified rectangular area.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `start` | `Vec2` | The starting point of the shadow rectangle. |
| `end_` | `Vec2` | The ending point of the shadow rectangle. |
| `color` | `Color` | The color of the shadow. |
| `thickness` | `number` | The thickness of the shadow. |
| `obj_rounding` *(optional)* | `number` | Default: `0.0`. The rounding radius of the shadow rectangle corners. |
| `flags` *(optional)* | `Enum.DrawFlags` | Default: `Enum.DrawFlags.ShadowCutOutShapeBackground`. Custom flags for drawing the shadow. |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. The offset of the shadow from the original rectangle. |

**Returns:** `nil`

### `Render.ShadowCircle(center, radius, color, thickness, num_segments?, flags?, offset?)`

Draws a circle shadow effect.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `center` | `Vec2` | The center point of the circle. |
| `radius` | `number` | The radius of the circle. |
| `color` | `Color` | The color of the shadow. |
| `thickness` | `number` | The thickness of the shadow. |
| `num_segments` *(optional)* | `integer` | Default: `12`. The number of segments for drawing the circle. |
| `flags` *(optional)* | `Enum.DrawFlags` | Default: `Enum.DrawFlags.ShadowCutOutShapeBackground`. Custom flags for drawing the shadow. |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. The offset of the shadow from the circle. |

**Returns:** `nil`

### `Render.ShadowConvexPoly(points, color, thickness, flags?, offset?)`

Draws a shadow convex polygon effect.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `points` | `Vec2[]` | Table of Vec2 points defining the convex polygon. Should be more than 2 points. |
| `color` | `Color` | The color of the shadow. |
| `thickness` | `number` | The thickness of the shadow. |
| `flags` *(optional)* | `Enum.DrawFlags` | Default: `Enum.DrawFlags.ShadowCutOutShapeBackground`. Custom flags for drawing the shadow. |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. The offset of the shadow from the polygon. |

**Returns:** `nil`

### `Render.ShadowNGon(center, radius, color, thickness, num_segments, flags?, offset?)`

Draws a shadow n-gon (polygon with n sides) effect.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `center` | `Vec2` | The center point of the n-gon. |
| `radius` | `number` | The radius of the n-gon. |
| `color` | `Color` | The color of the shadow. |
| `thickness` | `number` | The thickness of the shadow. |
| `num_segments` | `integer` | The number of segments (sides) of the n-gon. |
| `flags` *(optional)* | `Enum.DrawFlags` | Default: `Enum.DrawFlags.ShadowCutOutShapeBackground`. Custom flags for drawing the shadow. |
| `offset` *(optional)* | `Vec2` | Default: `{0.0, 0.0}`. The offset of the shadow from the n-gon. |

**Returns:** `nil`

### `Render.Blur(start, end_, strength?, alpha?, rounding?, flags?)`

Applies a blur effect within a specified rectangular area.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `start` | `Vec2` | The starting point of the blur rectangle. |
| `end_` | `Vec2` | The ending point of the blur rectangle. |
| `strength` *(optional)* | `number` | Default: `1.0`. The strength of the blur effect. |
| `alpha` *(optional)* | `number` | Default: `1.0`. The alpha value of the blur effect. |
| `rounding` *(optional)* | `number` | Default: `0.0`. The rounding radius of the blur rectangle corners. |
| `flags` *(optional)* | `Enum.DrawFlags` | Default: `Enum.DrawFlags.None`. Custom flags for the blur effect. |

**Returns:** `nil`

### `Render.PushClip(start, end_, intersect?)`

Begins a new clipping region. Only the rendering within the specified rectangular area will be displayed.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `start` | `Vec2` | The starting point of the clipping rectangle. |
| `end_` | `Vec2` | The ending point of the clipping rectangle. |
| `intersect` *(optional)* | `boolean` | Default: `false`. If true, the new clipping area is intersected with the current clipping area. |

**Returns:** `nil`

### `Render.PopClip()`

Ends the most recently begun clipping region, restoring the previous clipping region.

**Returns:** `nil`

### `Render.StartRotation(angle)`

Begins a new rotation.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `angle` | `number` | The rotation angle. |

**Returns:** `nil`

### `Render.StopRotation()`

End the rotation.

**Returns:** `nil`

### `Render.SetGlobalAlpha(alpha)`

Set the global alpha value for rendering.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `alpha` | `number` | The alpha value to set [0..1] |

**Returns:** `nil`

### `Render.ResetGlobalAlpha()`

Reset the global alpha value for rendering to 1.0.

**Returns:** `nil`

## Vertex

Vertex for use with `Render.TexturedPoly`.

### Fields

| Name | Type | Description |
|------|------|-------------|
| `pos` | `Vec2` | Vertex screen position. |
| `uv` | `Vec2` | Texture UV coordinates. |

### `Vertex(pos, uv)`

Creates a new Vertex.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pos` | `Vec2` | Vertex screen position. |
| `uv` | `Vec2` | Texture UV coordinates. |

**Returns:** `Vertex`

## CPanoramaImageName

Panorama image name handle.

### Methods

#### `CPanoramaImageName:get_name()`

Returns the Panorama symbol string for this image.

**Returns:** `string`

#### `CPanoramaImageName:get_file_path()`

Returns the file path of this image resource.

**Returns:** `string`

#### `CPanoramaImageName:is_empty()`

Returns whether this image is empty/unset.

**Returns:** `boolean`
