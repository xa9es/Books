# Get

## GetMousePosition
```lua
getmouseposition()
```
Returns the current mouse cursor position coordinates `{x, y}`

## SmoothMouse_Exponential
```lua
smooth_mouse_expontential(origin, point, speed)
```
Returns smoothed coordinates using exponential smoothing algorithm. Recommended for aimbot implementations.

Parameters:
- `origin`: Current position as {x, y}
- `point`: Target position as {x, y}
- `speed`: Smoothing speed factor

Returns: `{x, y}`

## SmoothMouse_Linear
```lua
smoothmouse_linear(origin, point, sensitivity, smoothness)
```
Returns smoothed coordinates using linear smoothing algorithm. Recommended for aimbot implementations.

Parameters:
- `origin`: Current position as {x, y}
- `point`: Target position as {x, y}
- `sensitivity`: Sensitivity factor
- `smoothness`: Smoothness factor

Returns: `{x, y}`

# Set

## MouseMoveRel
```lua
mousemoverel(x, y)
```
Moves the mouse cursor by the relative X and Y coordinates `void`

## MouseMoveAbs
```lua
mousemoveabs(x, y)
```
Moves the mouse cursor to the absolute X and Y coordinates `void`

## MouseScroll
```lua
mousescroll(pixels)
```
Scrolls the mouse wheel by the specified number of pixels `void`

## Mouse1Click
```lua
mouse1click()
```
Simulates a left mouse button click `void`

## Mouse1Press
```lua
mouse1press()
```
Simulates a left mouse button press (without release) `void`

## Mouse1Release
```lua
mouse1release()
```
Simulates a left mouse button release `void`

## Mouse2Click
```lua
mouse2click()
```
Simulates a right mouse button click `void`

## Mouse2Press
```lua
mouse2press()
```
Simulates a right mouse button press (without release) `void`

## Mouse2Release
```lua
mouse2release()
```
Simulates a right mouse button release `void`

# Check

## IsLeftClicked
```lua
isleftclicked()
```
Returns a boolean indicating if the left mouse button was clicked `boolean`

## IsRightClicked
```lua
isrightclicked()
```
Returns a boolean indicating if the right mouse button was clicked `boolean`

## IsLeftPressed
```lua
isleftpressed()
```
Returns a boolean indicating if the left mouse button is currently pressed `boolean`

## IsRightPressed
```lua
isrightpressed()
```
Returns a boolean indicating if the right mouse button is currently pressed `boolean`

# Examples