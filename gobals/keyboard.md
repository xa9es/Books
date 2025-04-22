---
description: Functions for keyboard input detection and simulation
---

# Keyboard

{% hint style="info" %}
Virtual key codes reference: [Microsoft Documentation](https://docs.microsoft.com/en-us/windows/desktop/inputdev/virtual-key-codes)
{% endhint %}

## Input Detection

### GetPressedKey

```lua
getpressedkey()
```

Returns the last pressed key name.

Returns: <kbd><mark style="color:yellow;">**string**<mark style="color:yellow;"></kbd> Key name

### GetPressedKeys

```lua
getpressedkeys()
```

Returns a list of currently pressed key names.

Returns: <kbd>**array**</kbd> Array of <kbd><mark style="color:yellow;">**string**<mark style="color:yellow;"></kbd> key names

## Input Simulation

### KeyPress

```lua
keypress(keycode)
```

Simulates a key press for the given virtual keycode.

Parameters:

* <kbd><mark style="color:blue;">**number**<mark style="color:blue;"></kbd>`keycode`: Virtual key code to simulate

Returns: <kbd><mark style="color:orange;">**void**<mark style="color:orange;"></kbd>

### KeyRelease

```lua
keyrelease(keycode)
```

Simulates a key release for the given virtual keycode.

Parameters:

* <kbd><mark style="color:blue;">**number**<mark style="color:blue;"></kbd>`keycode`: Virtual key code to simulate

Returns: <kbd><mark style="color:orange;">**void**<mark style="color:orange;"></kbd>
