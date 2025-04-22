---
description: The Drawing library provides functions for creating and manipulating 2D graphics elements on the screen overlay.
---

## Core Methods

### Drawing.new
```lua
Drawing.new(type)
```
Creates a new drawing object of the specified type.

Parameters:
* <kbd><mark style="color:yellow;">**string**</mark></kbd>`type`: The type of drawing object to create
  - Supported types: `"Text"`, `"Line"`, `"Quad"`, `"Triangle"`, `"Circle"`, `"Square"`, `"Image"`

Returns: <kbd><mark style="color:red;">**Instance**</mark></kbd> Drawing object

See: [@examples/watermark](../examples/watermark.md)

### Drawing.clear
```lua
Drawing.clear()
```
Clears and deletes all created drawing objects.

Returns: <kbd><mark style="color:orange;">**void**</mark></kbd>

## Common Properties
All drawing objects share these properties:

* <kbd><mark style="color:orange;">**boolean**</mark></kbd>`Visible` : Controls whether the object is visible
* <kbd><mark style="color:pink;">**function**</mark></kbd>`Remove` : Removes/destroys the drawing object
* <kbd><mark style="color:cyan;">**vector3**</mark></kbd>`Color` : RGB color of the object (values range from 0-255)
* <kbd><mark style="color:blue;">**number**</mark></kbd>`zIndex` : Controls the stacking order (higher values appear on top)

## Drawing Objects

### Text Object
Properties:
* <kbd><mark style="color:yellow;">**string**</mark></kbd>`Text` : The text content to display
* <kbd><mark style="color:blue;">**number**</mark></kbd>`Transparency` : Opacity value from 0 (invisible) to 1 (opaque)
* <kbd><mark style="color:blue;">**number**</mark></kbd>`Size` : Font size
* <kbd><mark style="color:orange;">**boolean**</mark></kbd>`Center` : Whether text should be centered
* <kbd><mark style="color:orange;">**boolean**</mark></kbd>`Outline` : Whether text should have an outline
* <kbd><mark style="color:cyan;">**vector3**</mark></kbd>`OutlineColor` : RGB color of the outline
* <kbd><mark style="color:cyan;">**vector2**</mark></kbd>`Position` : Screen position coordinates
* <kbd><mark style="color:cyan;">**vector2**</mark></kbd>`TextBounds` : Read-only size of the text (width and height)
* <kbd><mark style="color:purple;">**enum**</mark></kbd>`Font` : Font style (values 0-15)

### Line Object
Properties:
* <kbd><mark style="color:blue;">**number**</mark></kbd>`Transparency` : Opacity value from 0 (invisible) to 1 (opaque)
* <kbd><mark style="color:blue;">**number**</mark></kbd>`Thickness` : Line thickness in pixels
* <kbd><mark style="color:cyan;">**vector2**</mark></kbd>`From` : Starting point coordinates
* <kbd><mark style="color:cyan;">**vector2**</mark></kbd>`To` : Ending point coordinates

### Circle Object
Properties:
* <kbd><mark style="color:blue;">**number**</mark></kbd>`Transparency` : Opacity value from 0 (invisible) to 1 (opaque)
* <kbd><mark style="color:blue;">**number**</mark></kbd>`Thickness` : Border thickness in pixels
* <kbd><mark style="color:blue;">**number**</mark></kbd>`NumSides` : Number of sides (higher values create smoother circles)
* <kbd><mark style="color:blue;">**number**</mark></kbd>`Radius` : Circle radius in pixels
* <kbd><mark style="color:orange;">**boolean**</mark></kbd>`Filled` : Whether the circle should be filled
* <kbd><mark style="color:cyan;">**vector2**</mark></kbd>`Position` : Center position coordinates

### Square Object
Properties:
* <kbd><mark style="color:blue;">**number**</mark></kbd>`Transparency` : Opacity value from 0 (invisible) to 1 (opaque)
* <kbd><mark style="color:blue;">**number**</mark></kbd>`Thickness` : Border thickness in pixels
* <kbd><mark style="color:cyan;">**vector2**</mark></kbd>`Size` : Width and height dimensions
* <kbd><mark style="color:cyan;">**vector2**</mark></kbd>`Position` : Top-left position coordinates
* <kbd><mark style="color:orange;">**boolean**</mark></kbd>`Filled` : Whether the square should be filled

### Triangle Object
Properties:
* <kbd><mark style="color:blue;">**number**</mark></kbd>`Transparency` : Opacity value from 0 (invisible) to 1 (opaque)
* <kbd><mark style="color:blue;">**number**</mark></kbd>`Thickness` : Border thickness in pixels
* <kbd><mark style="color:cyan;">**vector2**</mark></kbd>`PointA` : First vertex coordinates
* <kbd><mark style="color:cyan;">**vector2**</mark></kbd>`PointB` : Second vertex coordinates
* <kbd><mark style="color:cyan;">**vector2**</mark></kbd>`PointC` : Third vertex coordinates
* <kbd><mark style="color:orange;">**boolean**</mark></kbd>`Filled` : Whether the triangle should be filled

### Image Object
Properties:
* <kbd><mark style="color:yellow;">**string**</mark></kbd>`Url` : URL of the image to display
* <kbd><mark style="color:orange;">**boolean**</mark></kbd>`Gif` : Whether the image is an animated GIF
* <kbd><mark style="color:blue;">**number**</mark></kbd>`Delay` : Frame delay for GIF animations
* <kbd><mark style="color:cyan;">**vector2**</mark></kbd>`Position` : Top-left position coordinates
* <kbd><mark style="color:cyan;">**vector2**</mark></kbd>`Size` : Width and height dimensions
* <kbd><mark style="color:blue;">**number**</mark></kbd>`Transparency` : Opacity value from 0 (invisible) to 1 (opaque)

### Quad Object
Properties:
* <kbd><mark style="color:cyan;">**vector2**</mark></kbd>`PointA` : First vertex coordinates
* <kbd><mark style="color:cyan;">**vector2**</mark></kbd>`PointB` : Second vertex coordinates
* <kbd><mark style="color:cyan;">**vector2**</mark></kbd>`PointC` : Third vertex coordinates
* <kbd><mark style="color:cyan;">**vector2**</mark></kbd>`PointD` : Fourth vertex coordinates
* <kbd><mark style="color:blue;">**number**</mark></kbd>`Thickness` : Border thickness in pixels
* <kbd><mark style="color:orange;">**boolean**</mark></kbd>`Filled` : Whether the quad should be filled
* <kbd><mark style="color:blue;">**number**</mark></kbd>`Transparency` : Opacity value from 0 (invisible) to 1 (opaque)


# Example

Watermark: [@examples/watermark](../examples/watermark.md)