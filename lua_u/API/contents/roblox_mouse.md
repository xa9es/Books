
{% hint style="hint" %}
game -> userinputservice
{% endhint %}

# Get

## GetMouseLocation
```lua
getmouselocation(userinputservice)
```
Returns the Roblox mouse cursor location coordinates `{x, y}`

## GetMouseBehavior
```lua
getmousebehavior(userinputservice)
```
Returns the current mouse behavior setting (0 = Default, 1 = LockCenter, 2 = LockCurrentPosition) `number`

## GetMouseDeltaSensitivity
```lua
getmousedeltasensitivity(userinputservice)
```
Returns the current mouse delta sensitivity setting `number`

# Set
## SetMouseLocation
```lua
setmouselocation(userinputservice, x, y)
```
Sets Roblox mouse location to specified X and Y coordinates `void`

## SetMouseIconEnabled
```lua
setmouseiconenabled(userinputservice, boolean)
```
Sets Roblox mouse icon visibility (false = hide cursor, true = show cursor) `void`

## SetMouseBehaviour
```lua
setmousebehaviour(userinputservice, number)
```
Sets Roblox mouse behaviour (0 = Default, 1 = LockCenter, 2 = LockCurrentPosition) `void`

## SetMouseDeltaSensitivity
```lua
setmousedeltasensitivity(userinputservice, number)
```
Sets Roblox mouse delta sensitivity `void`

# Check
## IsMouseIconEnabled
```lua
ismouseiconenabled(userinputservice)
```
Returns a boolean indicating if the mouse cursor icon is visible `boolean`