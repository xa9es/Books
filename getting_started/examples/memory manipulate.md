# Memory Manipulate

{% hint style="warning" %}
Offsets uses in examples are OUTDATED, take them as syntax examples
{% endhint %}

### Fake Client-Side Headless

{% hint style="info" %}
You either need to zoom in max and out OR execute the script upon resetting on your character to see the changes.
{% endhint %}

{% code title="headless.lua" overflow="wrap" %}
```lua
local head = game.Players.localPlayer.Character.Head
local primitive_ptr = head:GetMemoryValue(0x160, "qword")
local primitive_ptr_data = pointer_to_table_data(primitive_ptr)
primitive_ptr_data:SetMemoryValue(0x2ac, "float", 0) -- x
primitive_ptr_data:SetMemoryValue(0x2ac, "float", 0) -- y
primitive_ptr_data:SetMemoryValue(0x2ac, "float", 0) -- z
```
{% endcode %}

### Changing LocalPlayer Username (Client-Side)

{% code title="username.lua" overflow="wrap" fullWidth="false" %}
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
{% endcode %}
