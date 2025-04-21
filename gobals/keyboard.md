# Keyboard

Virtual key codes reference: [Microsoft Documentation](https://docs.microsoft.com/en-us/windows/desktop/inputdev/virtual-key-codes)

# Set

## KeyPress
```lua
keypress(keycode)
```
Simulates a key press for the given virtual keycode

## KeyRelease
```lua
keyrelease(keycode)
```
Simulates a key release for the given virtual keycode

# Get

## GetPressedKey
```lua
getpressedkey()
```
Returns the last pressed key name `string`

## GetPressedKeys
```lua
getpressedkeys()
```
Returns a list of currently pressed key names `table` 