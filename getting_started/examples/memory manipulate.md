
{% hint style="warning" %}
Offsets uses in examples might be outdated !
{% endhint %}
# Examples

## Fake Client-Side Headless

{% hint style="hint" %}
You either need to zoom in max and out OR execute the script upon resetting on your character to see the changes. 
{% endhint %}

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
setmemoryvalue(nameptr_data, 0x0, "string", "Niggachain_AI_Layer_2")
```