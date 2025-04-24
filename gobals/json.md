---
description: Functions for JSON encoding and decoding
---

## Methods

### JSONEncode
```lua
JSONEncode(table)
```
Converts a Lua table to a JSON formatted string.

Parameters:
* <kbd><mark style="color:green;">**table**</mark></kbd>`table`: The table to encode

Returns: <kbd><mark style="color:yellow;">**string**</mark></kbd> JSON formatted string

### JSONDecode
```lua
JSONDecode(string)
```
Converts a JSON formatted string to a Lua table.

Parameters:
* <kbd><mark style="color:yellow;">**string**</mark></kbd>`string`: The JSON string to decode

Returns: <kbd><mark style="color:green;">**table**</mark></kbd> Decoded table