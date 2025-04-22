---
description: >-
  The Drawing library provides functions for creating and manipulating 2D
  graphics elements on the screen overlay.
---

# Drawing

## Core Methods

### Drawing.new

```lua
Drawing.new(type)
```

Creates a new drawing object of the specified type.

Parameters:

* <kbd><mark style="color:yellow;">**string**<mark style="color:yellow;"></kbd>`type`: The type of drawing object to create
  * Supported types: `"Text"`, `"Line"`, `"Quad"`, `"Triangle"`, `"Circle"`, `"Square"`, `"Image"`

Returns: <kbd><mark style="color:red;">**Instance**<mark style="color:red;"></kbd> Drawing object

### Drawing.clear

```lua
Drawing.clear()
```

Clears and deletes all created drawing objects.

Returns: <kbd><mark style="color:orange;">**void**<mark style="color:orange;"></kbd>

### Common Properties

All drawing objects share these properties:

* <kbd><mark style="color:orange;">**boolean**<mark style="color:orange;"></kbd>`Visible` : Controls whether the object is visible
* <kbd>**function**</kbd>`Remove` : Removes/destroys the drawing object
* <kbd>**vector3**</kbd>`Color` : RGB color of the object (values range from 0-255)
* <kbd><mark style="color:blue;">**number**<mark style="color:blue;"></kbd>`zIndex` : Controls the stacking order (higher values appear on top)

## Drawing Objects

#### Text Object

Properties:

* <kbd><mark style="color:yellow;">**string**<mark style="color:yellow;"></kbd>`Text` : The text content to display
* <kbd><mark style="color:blue;">**number**<mark style="color:blue;"></kbd>`Transparency` : Opacity value from 0 (invisible) to 1 (opaque)
* <kbd><mark style="color:blue;">**number**<mark style="color:blue;"></kbd>`Size` : Font size
* <kbd><mark style="color:orange;">**boolean**<mark style="color:orange;"></kbd>`Center` : Whether text should be centered
* <kbd><mark style="color:orange;">**boolean**<mark style="color:orange;"></kbd>`Outline` : Whether text should have an outline
* <kbd>**vector3**</kbd>`OutlineColor` : RGB color of the outline
* <kbd>**vector2**</kbd>`Position` : Screen position coordinates
* <kbd>**vector2**</kbd>`TextBounds` : Read-only size of the text (width and height)
* <kbd><mark style="color:purple;">**enum**<mark style="color:purple;"></kbd>`Font` : Font style (values 0-15)

#### Line Object

Properties:

* <kbd><mark style="color:blue;">**number**<mark style="color:blue;"></kbd>`Transparency` : Opacity value from 0 (invisible) to 1 (opaque)
* <kbd><mark style="color:blue;">**number**<mark style="color:blue;"></kbd>`Thickness` : Line thickness in pixels
* <kbd>**vector2**</kbd>`From` : Starting point coordinates
* <kbd>**vector2**</kbd>`To` : Ending point coordinates

#### Circle Object

Properties:

* <kbd><mark style="color:blue;">**number**<mark style="color:blue;"></kbd>`Transparency` : Opacity value from 0 (invisible) to 1 (opaque)
* <kbd><mark style="color:blue;">**number**<mark style="color:blue;"></kbd>`Thickness` : Border thickness in pixels
* <kbd><mark style="color:blue;">**number**<mark style="color:blue;"></kbd>`NumSides` : Number of sides (higher values create smoother circles)
* <kbd><mark style="color:blue;">**number**<mark style="color:blue;"></kbd>`Radius` : Circle radius in pixels
* <kbd><mark style="color:orange;">**boolean**<mark style="color:orange;"></kbd>`Filled` : Whether the circle should be filled
* <kbd>**vector2**</kbd>`Position` : Center position coordinates

#### Square Object

Properties:

* <kbd><mark style="color:blue;">**number**<mark style="color:blue;"></kbd>`Transparency` : Opacity value from 0 (invisible) to 1 (opaque)
* <kbd><mark style="color:blue;">**number**<mark style="color:blue;"></kbd>`Thickness` : Border thickness in pixels
* <kbd>**vector2**</kbd>`Size` : Width and height dimensions
* <kbd>**vector2**</kbd>`Position` : Top-left position coordinates
* <kbd><mark style="color:orange;">**boolean**<mark style="color:orange;"></kbd>`Filled` : Whether the square should be filled

#### Triangle Object

Properties:

* <kbd><mark style="color:blue;">**number**<mark style="color:blue;"></kbd>`Transparency` : Opacity value from 0 (invisible) to 1 (opaque)
* <kbd><mark style="color:blue;">**number**<mark style="color:blue;"></kbd>`Thickness` : Border thickness in pixels
* <kbd>**vector2**</kbd>`PointA` : First vertex coordinates
* <kbd>**vector2**</kbd>`PointB` : Second vertex coordinates
* <kbd>**vector2**</kbd>`PointC` : Third vertex coordinates
* <kbd><mark style="color:orange;">**boolean**<mark style="color:orange;"></kbd>`Filled` : Whether the triangle should be filled

#### Image Object

Properties:

* <kbd><mark style="color:yellow;">**string**<mark style="color:yellow;"></kbd>`Url` : URL of the image to display
* <kbd><mark style="color:orange;">**boolean**<mark style="color:orange;"></kbd>`Gif` : Whether the image is an animated GIF
* <kbd><mark style="color:blue;">**number**<mark style="color:blue;"></kbd>`Delay` : Frame delay for GIF animations
* <kbd>**vector2**</kbd>`Position` : Top-left position coordinates
* <kbd>**vector2**</kbd>`Size` : Width and height dimensions
* <kbd><mark style="color:blue;">**number**<mark style="color:blue;"></kbd>`Transparency` : Opacity value from 0 (invisible) to 1 (opaque)

#### Quad Object

Properties:

* <kbd>**vector2**</kbd>`PointA` : First vertex coordinates
* <kbd>**vector2**</kbd>`PointB` : Second vertex coordinates
* <kbd>**vector2**</kbd>`PointC` : Third vertex coordinates
* <kbd>**vector2**</kbd>`PointD` : Fourth vertex coordinates
* <kbd><mark style="color:blue;">**number**<mark style="color:blue;"></kbd>`Thickness` : Border thickness in pixels
* <kbd><mark style="color:orange;">**boolean**<mark style="color:orange;"></kbd>`Filled` : Whether the quad should be filled
* <kbd><mark style="color:blue;">**number**<mark style="color:blue;"></kbd>`Transparency` : Opacity value from 0 (invisible) to 1 (opaque)

## Example

{% content-ref url="../getting_started/examples/watermark.md" %}
[watermark.md](../getting_started/examples/watermark.md)
{% endcontent-ref %}

{% content-ref url="../getting_started/examples/Gif_loading.md" %}
[Gif\_loading.md](../getting_started/examples/Gif_loading.md)
{% endcontent-ref %}
