# Types & Math

## Color

Color metatable

### Fields

| Name | Type | Description |
|------|------|-------------|
| `r` | `number` | red |
| `g` | `number` | green |
| `b` | `number` | blue |
| `a` | `number` | alpha |

### `Color(r?, g?, b?, a?)`

Create a new Color.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `r` *(optional)* | `number` | Default: `255` |
| `g` *(optional)* | `number` | Default: `255` |
| `b` *(optional)* | `number` | Default: `255` |
| `a` *(optional)* | `number` | Default: `255` |

**Returns:** `Color`

**Overloads:**

- `fun(hex: string): Color`
- `fun(rgba: number): Color`
- `fun(rgb: number, alpha: number): Color`
- `fun(r: number, g: number, b: number): Color`

### `_Color:AsFraction(r, g, b, a)`

Overwrites the color's ranges using the fraction values. Returns itself.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `r` | `number` | New R color range as a percentage in the range [0.0, 1.0] |
| `g` | `number` | New G color range as a percentage in the range [0.0, 1.0] |
| `b` | `number` | New B color range as a percentage in the range [0.0, 1.0] |
| `a` | `number` | New A color range as a percentage in the range [0.0, 1.0] |

**Returns:** `Color`

### `_Color:AsInt(value)`

Overwrites the color's ranges converting the int value to RGBA values. Returns\
itself.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `number` | int color value |

**Returns:** `Color`

### `_Color:AsHsv(h, s, v, a)`

Overwrites the color's ranges converting the HSV to RGBA values. Returns itself.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `h` | `number` | Hue color range [0.0, 1.0] |
| `s` | `number` | Saturation color range [0.0, 1.0] |
| `v` | `number` | Value color range [0.0, 1.0] |
| `a` | `number` | Alpha color range [0.0, 1.0] |

**Returns:** `Color`

### `_Color:AsHsl(h, s, l, a)`

Overwrites the color's ranges converting the HSL to RGBA values. Returns itself.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `h` | `number` | Hue color range [0.0, 1.0] |
| `s` | `number` | Saturation color range [0.0, 1.0] |
| `l` | `number` | Lightness color range [0.0, 1.0] |
| `a` | `number` | Alpha color range [0.0, 1.0] |

**Returns:** `Color`

### `_Color:ToFraction()`

Returns the r, g, b, and a ranges of the color as a percentage in the range of\
[0.0, 1.0].

**Returns:** `number` — r, `number` — g, `number` — b, `number` — a

### `_Color:ToInt()`

Returns the int value representing the color.

**Returns:** `number`

### `_Color:ToHsv()`

Returns the HSV representation of the color.

**Returns:** `number` — hue, `number` — saturation, `number` — value

### `_Color:ToHsl()`

Returns the ToHsl representation of the color.

**Returns:** `number` — hue, `number` — saturation, `number` — lightness

### `_Color:ToHex()`

Returns the hex string representing the color.

**Returns:** `string`

### `_Color:Lerp(other, weight)`

Returns the linearly interpolated color between two colors by the specified weight.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `other` | `Color` | The color to interpolate to |
| `weight` | `number` | A value between 0 and 1 that indicates the weight of **other** |

**Returns:** `Color`

### `_Color:Grayscale(weight)`

Returns the grayscaled color.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `weight` | `number` | A value between 0 and 1 that indicates the weight of **grayscale** |

**Returns:** `Color`

### `_Color:AlphaModulate(alpha)`

Returns the alpha modulated color.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `alpha` | `number` | Alpha color range [0.0, 1.0] |

**Returns:** `Color`

### `_Color:Clone()`

Creates and returns a copy of the color object.

**Returns:** `Color`

### `_Color:Unpack()`

Returns the r, g, b, and a values of the color. Note that these fields can be\
accessed by indexing r, g, b, and a.

**Returns:** `number` — r, `number` — g, `number` — b, `number` — a

### `_Color:__tostring()`

Returns hex string representing the color.

**Returns:** `string`

## Vec2

Vec2 metatable

### Fields

| Name | Type | Description |
|------|------|-------------|
| `x` | `number` |  |
| `y` | `number` |  |

### `Vec2(x, y)`

Create a new Vec2.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `x` | `number` |  |
| `y` | `number` |  |

**Returns:** `Vec2`

**Overloads:**

- `fun():Vec2`

### `_Vec2:__tostring()`

**Returns:** `string`

### `_Vec2:__add(other)`

> **Deprecated**

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `other` | `Vec2\|number` |  |

**Returns:** `Vec2`

### `_Vec2:__sub(other)`

> **Deprecated**

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `other` | `Vec2\|number` |  |

**Returns:** `Vec2`

### `_Vec2:__div(other)`

> **Deprecated**

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `other` | `Vec2\|number` |  |

**Returns:** `Vec2`

### `_Vec2:Length()`

Returns the length of the vector.

**Returns:** `number`

### `_Vec2:Get()`

Returns x, y of this vector.

**Returns:** `number` — x, `number` — y

### `_Vec2:GetX()`

> **Deprecated**

Returns x of this vector. The same as Vec2.x.

**Returns:** `number`

### `_Vec2:GetY()`

> **Deprecated**

Returns y of this vector. The same as Vec2.y.

**Returns:** `number`

### `_Vec2:SetX(value)`

> **Deprecated**

Sets x. The same as Vec2.x = value.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `number` |  |

**Returns:** `nil`

### `_Vec2:SetY(value)`

> **Deprecated**

Sets y. The same as Vec2.y = value.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `number` |  |

**Returns:** `nil`

## Vector

Vector metatable

### Fields

| Name | Type | Description |
|------|------|-------------|
| `x` | `number` |  |
| `y` | `number` |  |
| `z` | `number` |  |

### `Vector(x?, y?, z?)`

Create a new Vector.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `x` *(optional)* | `number` | Default: `0.0` |
| `y` *(optional)* | `number` | Default: `0.0` |
| `z` *(optional)* | `number` | Default: `0.0` |

**Returns:** `Vector`

### `_Vector:__tostring()`

**Returns:** `string`

### `_Vector:__add(other)`

> **Deprecated**

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `other` | `Vector\|Vec2\|number` |  |

**Returns:** `Vector`

### `_Vector:__sub(other)`

> **Deprecated**

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `other` | `Vector\|Vec2\|number` |  |

**Returns:** `Vector`

### `_Vector:__div(other)`

> **Deprecated**

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `other` | `Vector\|Vec2\|number` |  |

**Returns:** `Vector`

### `_Vector:__mul(other)`

> **Deprecated**

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `other` | `Vector\|Vec2\|number` |  |

**Returns:** `Vector`

### `_Vector:__eq(other)`

> **Deprecated**

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `other` | `Vector` |  |

**Returns:** `boolean`

### `_Vector:Distance(other)`

Computes the distance from this vector to other.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `other` | `Vector` |  |

**Returns:** `number`

### `_Vector:Distance2D(other)`

Computes the distance from this vector to other ignoring Z axis.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `other` | `Vector` |  |

**Returns:** `number`

### `_Vector:Normalized()`

Returns this vector with a length of 1.\
When normalized, a vector keeps the same direction but its length is 1.0.\
Note that the current vector is unchanged and a new normalized vector is returned. If you want to normalize the current vector, use `Vector:Normalize` function.

**Returns:** `Vector`

### `_Vector:Normalize()`

Makes this vector have a length of 1.\
When normalized, a vector keeps the same direction but its length is 1.0.\
Note that this function will change the current vector. If you want to keep the current vector unchanged, use `Vector:Normalized` function.

**Returns:** `nil`

### `_Vector:Dot(vector)`

Dot Product of two vectors.\
The dot product is a float value equal to the magnitudes of the two vectors multiplied together and then multiplied by the cosine of the angle between them.\
For normalized vectors Dot returns 1 if they point in exactly the same direction, -1 if they point in completely opposite directions and zero if the vectors are perpendicular. \
\
[More](https://medium.com/@r.w.overdijk/unity-vector3-dot-what-11feb258052e)

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `vector` | `Vector` |  |

**Returns:** `number`

### `_Vector:Dot2D(vector)`

Dot Product of two vectors ignoring Z axis.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `vector` | `Vector` |  |

**Returns:** `number`

### `_Vector:Scaled(scale)`

Returns this vector multiplied by the given number. The same as `Vector * number`.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `scale` | `number` |  |

**Returns:** `Vector`

### `_Vector:Scale(scale)`

Multiplies this vector by the given number. The same as `Vector = Vector * number`.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `scale` | `number` |  |

**Returns:** `nil`

### `_Vector:Length()`

Returns the length of this vector.\
The length of the vector is `math.sqrt(x*x+y*y+z*z)`.\
If you only need to compare length of some vectors, you can compare squared magnitudes of them using LengthSqr (computing squared length is faster).

**Returns:** `number`

### `_Vector:LengthSqr()`

Returns the squared length of this vector.\
This method is faster than Length because it avoids computing a square root. Use this method if you need to compare vectors.

**Returns:** `number`

### `_Vector:Length2D()`

Returns the length of this vector ignoring Z axis.

**Returns:** `number`

### `_Vector:Length2DSqr()`

Returns the squared length of this vector ignoring Z axis.\
This method is faster than Length2D because it avoids computing a square root. Use this method if you need to compare vectors.

**Returns:** `number`

### `_Vector:Rotated(angle)`

Returns the new vector rotated counterclockwise by the given angle in the XY-plane, leaving the Z-axis unaffected.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `angle` | `number\|Angle` |  |

**Returns:** `Vector`

### `_Vector:Rotate(angle)`

Rotates this vector counterclockwise by the given angle in the XY-plane, leaving the Z-axis unaffected.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `angle` | `number\|Angle` |  |

**Returns:** `nil`

### `_Vector:Lerp(b, t)`

Returns linearly interpolated vector between two vectors.\
The value returned equals **a + (b - a) * t** (which can also be written **a * (1-t) + b*t**).\
When `t = 0`, **a:Lerp(b, t)** returns `a`.\
When `t = 1`, **a:Lerp(b, t)** returns `b`.\
When `t = 0.5`, **a:Lerp(b, t)** returns the point midway between `a` and `b`.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `b` | `Vector` | end value, returned when t = 1 |
| `t` | `number` | value used to interpolate between a and b. |

**Returns:** `Vector`

### `_Vector:Cross(vector)`

Returns cross product of two vectors.\
\
[More](https://docs.unity3d.com/ScriptReference/Vector3.Cross.html)\
[Visualization](https://www.youtube.com/watch?v=kz92vvioeng)

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `vector` | `Vector` |  |

**Returns:** `Vector`

### `_Vector:MoveForward(angle, distance)`

Moves vector forward by a specified distance in the direction defined by a given Angle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `angle` | `Angle` |  |
| `distance` | `number` | distance to move |

**Returns:** `Vector`

### `_Vector:ToAngle()`

Converts Vector to Angle. See\
https://github.com/ValveSoftware/source-sdk-2013/blob/0565403b153dfcde602f6f58d8f4d13483696a13/src/mathlib/mathlib_base.cpp#L535

**Returns:** `Vector`

### `_Vector:ToScreen()`

Converts Vector to screen coordinate

**Returns:** `Vec2` — screenPos, `boolean` — isVisible

### `_Vector:Get()`

Returns x, y and z of this vector.

**Returns:** `number` — x, `number` — y, `number` — z

### `_Vector:GetX()`

> **Deprecated**

Returns x of this vector. The same as Vector.x.

**Returns:** `number`

### `_Vector:GetY()`

> **Deprecated**

Returns y of this vector. The same as Vector.y.

**Returns:** `number`

### `_Vector:GetZ()`

> **Deprecated**

Returns z of this vector. The same as Vector.z.

**Returns:** `number`

### `_Vector:SetX(value)`

> **Deprecated**

Sets x. The same as Vector.x = value.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `number` |  |

**Returns:** `nil`

### `_Vector:SetY(value)`

> **Deprecated**

Sets y. The same as Vector.y = value.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `number` |  |

**Returns:** `nil`

### `_Vector:SetZ(value)`

> **Deprecated**

Sets z. The same as Vector.z = value.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `number` |  |

**Returns:** `nil`

### `_Vector:Normalize()`

**Returns:** `nil`

### `_Vector:Clamp()`

### `_Vector:IsInvalid()`

**Returns:** `boolean`

## Angle

Angle metatable

### Fields

| Name | Type | Description |
|------|------|-------------|
| `pitch` | `number` |  |
| `yaw` | `number` |  |
| `roll` | `number` |  |

### `Angle(pitch?, yaw?, roll?)`

Create a new Angle.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pitch` *(optional)* | `number` | Default: `0.0` |
| `yaw` *(optional)* | `number` | Default: `0.0` |
| `roll` *(optional)* | `number` | Default: `0.0` |

**Returns:** `Angle`

### `_Angle:__tostring()`

**Returns:** `string`

### `_Angle:GetForward()`

Returns the forward vector from a given Angle.

**Returns:** `Vector`

### `_Angle:GetVectors()`

Returns the forward, right and up.

**Returns:** `Vector` — forward, `Vector` — right, `Vector` — up

### `_Angle:GetYaw()`

> **Deprecated**

Returns the yaw. The same as Angle.yaw.

**Returns:** `number`

### `_Angle:GetRoll()`

> **Deprecated**

Returns the roll. The same as Angle.roll.

**Returns:** `number`

### `_Angle:GetPitch()`

> **Deprecated**

Returns the pitch. The same as Angle.pitch.

**Returns:** `number`

### `_Angle:SetYaw(value)`

> **Deprecated**

Sets the yaw. The same as Angle.yaw = value.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `number` |  |

**Returns:** `nil`

### `_Angle:SetRoll(value)`

> **Deprecated**

Sets the roll. The same as Angle.roll = value.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `number` |  |

**Returns:** `nil`

### `_Angle:SetPitch(value)`

> **Deprecated**

Sets the pitch. The same as Angle.pitch = value.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `value` | `number` |  |

**Returns:** `nil`

### `_Angle:Normalize()`

**Returns:** `nil`
