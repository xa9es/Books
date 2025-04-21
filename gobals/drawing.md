---
description: The Drawing library provides functions for creating and manipulating 2D graphics elements on the screen overlay.
---
# Methods
## Drawing.new
```lua
Drawing.new(type)
```
Creates a new drawing object of the specified type `object`

Supported types:
- `"Text"`
- `"Line"`
- `"Quad"`
- `"Triangle"`
- `"Circle"`
- `"Square"`
- `"Image"`

## Drawing.clear
```lua
Drawing.clear()
```
Clears and deletes all created drawing objects `void`

# Common Properties

All drawing objects share these properties:

- `Visible` (boolean): Controls whether the object is visible
- `Remove` (function): Removes/destroys the drawing object
- `Color` (Vector3): RGB color of the object (values range from 0-255)
- `zIndex` (number): Controls the stacking order (higher values appear on top)

# Object-Specific Properties

## Text Properties
- `Text` (string): The text content to display
- `Transparency` (number): Opacity value from 0 (invisible) to 1 (opaque)
- `Size` (number): Font size
- `Center` (boolean): Whether text should be centered
- `Outline` (boolean): Whether text should have an outline
- `OutlineColor` (Vector3): RGB color of the outline
- `Position` (Vector2): Screen position coordinates
- `TextBounds` (Vector2): Read-only size of the text (width and height)
- `Font` (number): Font style (values 0-15)

## Line Properties
- `Transparency` (number): Opacity value from 0 (invisible) to 1 (opaque)
- `Thickness` (number): Line thickness in pixels
- `From` (Vector2): Starting point coordinates
- `To` (Vector2): Ending point coordinates

## Circle Properties
- `Transparency` (number): Opacity value from 0 (invisible) to 1 (opaque)
- `Thickness` (number): Border thickness in pixels
- `NumSides` (number): Number of sides (higher values create smoother circles)
- `Radius` (number): Circle radius in pixels
- `Filled` (boolean): Whether the circle should be filled
- `Position` (Vector2): Center position coordinates

## Square Properties
- `Transparency` (number): Opacity value from 0 (invisible) to 1 (opaque)
- `Thickness` (number): Border thickness in pixels
- `Size` (Vector2): Width and height dimensions
- `Position` (Vector2): Top-left position coordinates
- `Filled` (boolean): Whether the square should be filled

## Triangle Properties
- `Transparency` (number): Opacity value from 0 (invisible) to 1 (opaque)
- `Thickness` (number): Border thickness in pixels
- `PointA` (Vector2): First vertex coordinates
- `PointB` (Vector2): Second vertex coordinates
- `PointC` (Vector2): Third vertex coordinates
- `Filled` (boolean): Whether the triangle should be filled

## Image Properties
- `Url` (string): URL of the image to display
- `Gif` (boolean): Whether the image is an animated GIF
- `Delay` (number): Frame delay for GIF animations
- `Position` (Vector2): Top-left position coordinates
- `Size` (Vector2): Width and height dimensions
- `Transparency` (number): Opacity value from 0 (invisible) to 1 (opaque)

## Quad Properties
- `PointA` (Vector2): First vertex coordinates
- `PointB` (Vector2): Second vertex coordinates
- `PointC` (Vector2): Third vertex coordinates
- `PointD` (Vector2): Fourth vertex coordinates
- `Thickness` (number): Border thickness in pixels
- `Filled` (boolean): Whether the quad should be filled
- `Transparency` (number): Opacity value from 0 (invisible) to 1 (opaque)



## Animated GIF Example
```lua
local image = Drawing.new("Image")
image.Url = "https://i.giphy.com/media/v1.Y2lkPTc5MGI3NjExaTMzN21qODhla2pudGtlZHQ4aXpyMm5rOXlud3hkbjRmcm44MXhkdCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/VrQjb9El7JaQSFYjgJ/giphy-downsized-large.gif"
image.Visible = true
image.zIndex = 1
image.Gif = true
image.Delay = 30
image.Position = {400, 100}
image.Size = {500, 500}
wait(20) -- Display for 20 seconds
image:Remove()
```

## Static Image Example
```lua
local image = Drawing.new("Image")
image.Url = "https://letsenhance.io/static/8f5e523ee6b2479e26ecc91b9c25261e/1015f/MainAfter.jpg"
image.Visible = true
image.zIndex = 1
image.Position = {1000, 100}
image.Size = {500, 500}
wait(10) -- Display for 10 seconds
image:Remove()
``` 