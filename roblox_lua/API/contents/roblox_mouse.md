# Get

## GetMouseLocation
```lua
game:GetService("UserInputService"):GetMouseLocation()
```
Returns the Roblox mouse cursor location coordinates `{x, y}`

## GetMouseBehavior
```lua
game:GetService("UserInputService"):GetMouseBehavior()
```
Returns the current mouse behavior setting (0 = Default, 1 = LockCenter, 2 = LockCurrentPosition) `number`

## GetMouseDeltaSensitivity
```lua
game:GetService("UserInputService"):GetMouseDeltaSensitivity()
```
Returns the current mouse delta sensitivity setting `number`

# Set

## SetMouseLocation
```lua
game:GetService("UserInputService")::SetMouseLocation(number, number)
```
Sets Roblox mouse location to specified X and Y coordinates `void`

## SetMouseIconEnabled
```lua
game:GetService("UserInputService")::SetMouseIconEnabled(boolean)
```
Sets Roblox mouse icon visibility (false = hide cursor, true = show cursor) `void`

## SetMouseBehaviour
```lua
game:GetService("UserInputService")::SetMouseBehaviour(number)
```
Sets Roblox mouse behaviour (0 = Default, 1 = LockCenter, 2 = LockCurrentPosition) `void`

## SetMouseDeltaSensitivity
```lua
game:GetService("UserInputService")::SetMouseDeltaSensitivity(number)
```
Sets Roblox mouse delta sensitivity `void`