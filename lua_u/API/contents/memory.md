# Memory/Internal Functions

Functions for low-level memory access and manipulation.

# Types
- `qword` - 64-bit unsigned integer
- `dword` - 32-bit unsigned integer
- `double` - 64-bit floating point
- `float` - 32-bit floating point
- `string` - Text string
- `bool` - Boolean value

# Get

## getmemoryvalue
```lua
getmemoryvalue(pointer, offset, type)
```
Reads a value from memory at a specified offset from a pointer.

Parameters:
- `pointer` (userdata): Base memory pointer
- `offset` (number): Offset from the base pointer
- `type` (string): Type of value to read ("qword", "dword", "double", "float", "string", "bool")

Returns Value of the specified type at the memory location

# Set

## setmemoryvalue
```lua
setmemoryvalue(pointer, offset, type, value)
```
Writes a value to memory at a specified offset from a pointer.

Parameters:
- `pointer` (userdata): Base memory pointer
- `offset` (number): Offset from the base pointer
- `type` (string): Type of value to write ("qword", "dword", "double", "float", "string", "bool")
- `value` (number/string): Value to write to memory

Returns `void`

## pointer_to_table_data
```lua
pointer_to_table_data(pointer)
```
Converts a pointer number to a table usable for internal functions (Primarily for use with RLua).

Parameters:
- `pointer` (number): Memory address pointer

Returns `table` representation of the pointer

## pointer_to_user_data
```lua
pointer_to_user_data(pointer)
```
Converts a pointer number to a userdata object usable for internal functions.

Parameters:
- `pointer` (number): Memory address pointer

Returns `userdata` representation of the pointer

# Examples

## Fake Client-Side Headless
```lua
-- Modify the head mesh rendering by changing primitive size values to 0
local head = game.Players.localPlayer.Character.Head
local primitive_ptr = head:getmemoryvalue(0x160, "qword")
local primitive_ptr_data = pointer_to_table_data(primitive_ptr)
primitive_ptr_data:setmemoryvalue(0x2ac, "float", 0) -- x
primitive_ptr_data:setmemoryvalue(0x2ac, "float", 0) -- y
primitive_ptr_data:setmemoryvalue(0x2ac, "float", 0) -- z
```

## Changing LocalPlayer Username (Client-Side)
```lua
-- Access and modify the player's name in memory
local localplayer = getlocalplayer()
-- Get the memory value at offset: 0x68 with type: qword
local nameptr = getmemoryvalue(localplayer, 0x68, "qword")
-- Convert the pointer to a userdata so it can be used
local nameptr_data = pointer_to_user_data(nameptr)
-- Get the current name string at offset: 0x0
local name = getmemoryvalue(nameptr_data, 0x0, "string")
-- Print the current name
print(name)
-- Set a new name in memory
setmemoryvalue(nameptr_data, 0x0, "string", "hello_severe")
```

# Notes
- Memory manipulation is extremely powerful but should be used with caution
- Incorrect memory access can cause crashes or unexpected behavior
- Memory offsets may change with Roblox updates
- These functions provide client-side changes only
- Always validate pointers before attempting to read or write memory