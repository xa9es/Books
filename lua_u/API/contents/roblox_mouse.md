
# Get

## GetMouseLocation
```lua
getmouselocation(getservice(Game, "UserInputService"))
```
Returns the Roblox mouse cursor location coordinates `{x, y}`

## GetMouseBehavior
```lua
getmousebehavior(getservice(Game, "UserInputService"))
```
Returns the current mouse behavior setting (0 = Default, 1 = LockCenter, 2 = LockCurrentPosition) `number`

## GetMouseDeltaSensitivity
```lua
getmousedeltasensitivity(getservice(Game, "UserInputService"))
```
Returns the current mouse delta sensitivity setting `number`

# Set
## SetMouseLocation
```lua
setmouselocation(getservice(Game, "UserInputService"), x, y)
```
Sets Roblox mouse location to specified X and Y coordinates `void`

## SetMouseIconEnabled
```lua
setmouseiconenabled(getservice(Game, "UserInputService"), boolean)
```
Sets Roblox mouse icon visibility (false = hide cursor, true = show cursor) `void`

## SetMouseBehaviour
```lua
setmousebehaviour(getservice(Game, "UserInputService"), number)
```
Sets Roblox mouse behaviour (0 = Default, 1 = LockCenter, 2 = LockCurrentPosition) `void`

## SetMouseDeltaSensitivity
```lua
setmousedeltasensitivity(getservice(Game, "UserInputService"), number)
```
Sets Roblox mouse delta sensitivity `void`

# Check
## IsMouseIconEnabled
```lua
ismouseiconenabled(getservice(Game, "UserInputService"))
```
Returns a boolean indicating if the mouse cursor icon is visible `boolean`