---
description: Utilities are functions or properties that you can use in any script. Luau globals are native to Luau, while Roblox globals are found only on Roblox.
---

# Utility

## Console Output

### Print
```lua
print(string)
```
Prints out **white** text in the console.

Parameters:
* <kbd><mark style="color:yellow;">**string**</mark></kbd>`string`: Text to print

Returns: <kbd><mark style="color:orange;">**void**</mark></kbd>

### Warn
```lua
warn(string)
```
Prints out <mark style="color:red;">red</mark> text in the console.

Parameters:
* <kbd><mark style="color:yellow;">**string**</mark></kbd>`string`: Text to print as warning

Returns: <kbd><mark style="color:orange;">**void**</mark></kbd>

## Thread Control

### Wait
```lua
wait(number)
```
Specifies how long in seconds the thread should yield for.

Parameters:
* <kbd><mark style="color:blue;">**number**</mark></kbd>`number`: Time in seconds to wait

Returns: <kbd><mark style="color:orange;">**void**</mark></kbd>

### Spawn
```lua
spawn(function)
```
Spawns in a task which is executed in the scheduler.

Parameters:
* <kbd><mark style="color:pink;">**function**</mark></kbd>`function`: Function to execute in new thread

Returns: <kbd><mark style="color:brown;">**thread**</mark></kbd> New thread object

## System Functions

### Get HWID
```lua 
gethwid()
```
Returns current user HWID.

Returns: <kbd><mark style="color:yellow;">**string**</mark></kbd> Hardware ID

### Set Clipboard
```lua
setclipboard(string)
```
Sets the string argument to your clipboard.

Parameters:
* <kbd><mark style="color:yellow;">**string**</mark></kbd>`string`: Text to copy to clipboard

Returns: <kbd><mark style="color:orange;">**void**</mark></kbd>

### Tick
```lua
tick()
```
Returns how much time has elapsed, in seconds, since the UNIX epoch, on the current local session's computer.

Returns: <kbd><mark style="color:blue;">**number**</mark></kbd> Time in seconds

### Gcinfo
```lua
gcinfo()
```
Returns the total memory heap size in kilobytes.

Returns: <kbd><mark style="color:blue;">**number**</mark></kbd> Memory size in KB 