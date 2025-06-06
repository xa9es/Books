---
description: Functions for low-level memory access and manipulation.
---

# Memory

{% hint style="warning" %}
Memory manipulation is extremely powerful but should be used with caution\
Incorrect memory access can cause crashes or unexpected behavior\
Memory offsets may change with Roblox updates\
These functions provide client-side changes only\
Always validate pointers before attempting to read or write memory
{% endhint %}

## Types

* `qword` - 64-bit unsigned integer
* `dword` - 32-bit unsigned integer
* `double` - 64-bit floating point
* `float` - 32-bit floating point
* `string` - Text string
* `bool` - Boolean value

## Get

### GetMemoryValue

```lua
instance:GetMemoryValue(offset, type)
```

Reads a value from memory at a specified offset from a pointer.

Parameters:

* `pointer` (userdata): Base memory pointer
* `offset` (number): Offset from the base pointer
* `type` (string): Type of value to read ("qword", "dword", "double", "float", "string", "bool")

Returns value of the specified type at the memory location

### SetMemoryValue

```lua
instance:SetMemoryValue(offset, type, value)
```

Writes a value to memory at a specified offset from a pointer.

Parameters:

* `pointer` (userdata): Base memory pointer
* `offset` (number): Offset from the base pointer
* `type` (string): Type of value to write ("qword", "dword", "double", "float", "string", "bool")
* `value` (number/string): Value to write to memory

### PointerToTableData

```lua
PointerToTableData(pointer)
```

Converts a pointer number to a table usable for internal functions (Primarily for use with RLua).

Parameters:

* `pointer` (number): Memory address pointer

Returns `table` representation of the pointer

### PointerToUserData

```lua
PointerToUserData(pointer)
```

Converts a pointer number to a userdata object usable for internal functions.

Parameters:

* `pointer` (number): Memory address pointer

Returns `userdata` representation of the pointer

## Examples

{% content-ref url="../../../getting_started/examples/memory manipulate.md" %}
[memory manipulate.md](<../../../getting_started/examples/memory manipulate.md>)
{% endcontent-ref %}
