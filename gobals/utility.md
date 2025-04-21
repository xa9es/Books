---
description: Utilities are functions or properties that you can use in any script. Luau globals are native to Luau, while Roblox globals are found only on Roblox.
---
# Functions
## Print
```lua
print(string)
```
Prints out **white** text in the console

## Warn
```lua
warn(string)
```
Prints out <mark style="color:red;">red</mark> text in the console

## Wait
```lua
wait(number)
```
Specifies how long in `seconds` the thread should yield for.

## Spawn
```lua
spawn(function)
```
Spawns in a task which is executed in the scheduler

## Get HWID
```lua 
gethwid()
```
Returns current user HWID as `string`

## Set Clipboard
```lua
setclipboard(string)
```
Sets the string argument to your clipboard

## Tick
```lua
tick()
```
Returns how much time has elapsed, in seconds, since the UNIX epoch, on the current local session's computer. `number`

## Gcinfo
```lua
gcinfo()
```
Returns the total memory heap size in kilobytes. 