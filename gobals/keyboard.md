---
description: Functions for keyboard input detection and simulation
---

{% hint style="hint" %}
Virtual key codes reference: [Microsoft Documentation](https://docs.microsoft.com/en-us/windows/desktop/inputdev/virtual-key-codes)
{% endhint %}

## Input Detection

### GetPressedKey
```lua
getpressedkey()
```
Returns the last pressed key name.

Returns: <kbd><mark style="color:yellow;">**string**</mark></kbd> Key name

### GetPressedKeys
```lua
getpressedkeys()
```
Returns a list of currently pressed key names.

Returns: <kbd><mark style="color:teal;">**array**</mark></kbd> Array of <kbd><mark style="color:yellow;">**string**</mark></kbd> key names

## Input Simulation

### KeyPress
```lua
keypress(keycode)
```
Simulates a key press for the given virtual keycode.

Parameters:
* <kbd><mark style="color:blue;">**number**</mark></kbd>`keycode`: Virtual key code to simulate

Returns: <kbd><mark style="color:orange;">**void**</mark></kbd>

### KeyRelease
```lua
keyrelease(keycode)
```
Simulates a key release for the given virtual keycode.

Parameters:
* <kbd><mark style="color:blue;">**number**</mark></kbd>`keycode`: Virtual key code to simulate

Returns: <kbd><mark style="color:orange;">**void**</mark></kbd>

See: [@examples/basic_mouse_aimbot](../examples/basic_mouse_aimbot.md) for keyboard input usage examples.
