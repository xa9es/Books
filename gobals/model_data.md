---
description: >-
  This primarily for storing character-related information, used for gameplay
  logic such as targeting, visualization, and status tracking.
---

## Model Data Structure
Defines the structure for storing character-related information, used for gameplay logic such as targeting, visualization, and status tracking.

### Fields
* <kbd><mark style="color:yellow;">**string**</mark></kbd>`Username` : The player's in-game username
* <kbd><mark style="color:yellow;">**string**</mark></kbd>`Displayname` : The player's display name
* <kbd><mark style="color:blue;">**number**</mark></kbd>`Userid` : Unique player identifier (Roblox UserId)
* <kbd><mark style="color:red;">**userdata**</mark></kbd>`Character` : Reference to the character model userdata
* <kbd><mark style="color:red;">**userdata**</mark></kbd>`PrimaryPart` : The root/base part of the character (usually HumanoidRootPart)
* <kbd><mark style="color:red;">**userdata**</mark></kbd>`Head` : Head part of the character
* <kbd><mark style="color:red;">**userdata**</mark></kbd>`LeftLeg` : Left leg part
* <kbd><mark style="color:red;">**userdata**</mark></kbd>`LeftArm` : Left arm part
* <kbd><mark style="color:red;">**userdata**</mark></kbd>`RightLeg` : Right leg part
* <kbd><mark style="color:red;">**userdata**</mark></kbd>`RightArm` : Right arm part
* <kbd><mark style="color:red;">**userdata**</mark></kbd>`Torso` : Torso or central body part
* <kbd><mark style="color:blue;">**number**</mark></kbd>`BodyHeightScale` : Height scale multiplier for the character
* <kbd><mark style="color:blue;">**number**</mark></kbd>`RigType` : Rig type (e.g., "R6 = 0" or "R15 = 1")
* <kbd><mark style="color:orange;">**boolean**</mark></kbd>`Whitelisted` : Whether the player is excluded from hostile logic
* <kbd><mark style="color:orange;">**boolean**</mark></kbd>`Archenemies` : Designates a hostile player
* <kbd><mark style="color:red;">**userdata**</mark></kbd>`Aimbot_Part` : Preferred target part for aimbot functionality
* <kbd><mark style="color:red;">**userdata**</mark></kbd>`Aimbot_TP_Part` : Target part for aimbot teleportation (e.g., for mouse tp)
* <kbd><mark style="color:red;">**userdata**</mark></kbd>`Triggerbot_Part` : Part used for triggerbot activation
* <kbd><mark style="color:blue;">**number**</mark></kbd>`Health` : Current health value of the character
* <kbd><mark style="color:blue;">**number**</mark></kbd>`MaxHealth` : Maximum health value
* <kbd><mark style="color:green;">**table**</mark></kbd>`body_parts_data` : Table for specific body parts, typically used for chams & skeleton
  * Format: `{ name = "LowerTorso", part = userdata }`
* <kbd><mark style="color:green;">**table**</mark></kbd>`full_body_data` : Table for all relevant body parts, typically used for closest and random body parts
  * Format: `{ name = "Head", part = userdata }`

### Methods

#### add_model_data
```lua
add_model_data(data, key)
```
Creates model data with a specific key that will be processed in the model thread.

Parameters:
* `data` (table): Model data structure containing fields listed above
* `key` (string): Unique identifier for this model data

Returns <kbd><mark style="color:orange;">**boolean**</mark></kbd> - true if successful

Example:
```lua
local data = {
    Username = "Player1",
    Displayname = "CoolPlayer",
    Userid = 123456,
    Character = workspace.Player1.Character.Data,
    PrimaryPart = workspace.Player1.Character.HumanoidRootPart.Data,
    -- additional fields from above...
}
add_model_data(data, "key_1")
```

## Model Edit Structure
Defines a partial data structure intended to update specific fields of an existing model data.

### Fields
* <kbd><mark style="color:blue;">**number**</mark></kbd>`RigType` : Rig type (e.g., R6 = 0, R15 = 1)
* <kbd><mark style="color:orange;">**boolean**</mark></kbd>`Whitelisted` : Whether the player is excluded from hostile checks
* <kbd><mark style="color:orange;">**boolean**</mark></kbd>`Archenemies` : Designates a hostile player
* <kbd><mark style="color:red;">**userdata**</mark></kbd>`Aimbot_Part` : Target part for aimbot (usually the head)
* <kbd><mark style="color:red;">**userdata**</mark></kbd>`Aimbot_TP_Part` : Target part for teleporting with aimbot (default: head) (mouse tp)
* <kbd><mark style="color:red;">**userdata**</mark></kbd>`Triggerbot_Part` : Target part used by triggerbot
* <kbd><mark style="color:blue;">**number**</mark></kbd>`Health` : Updated current health
* <kbd><mark style="color:blue;">**number**</mark></kbd>`MaxHealth` : Updated max health capacity
* <kbd><mark style="color:blue;">**number**</mark></kbd>`BodyHeightScale` : Updated height scaling value

### Methods

#### edit_model_data
```lua
edit_model_data(data, key)
```
Edits existing model data for a specific key.

Parameters:
* `data` (table): Partial model data structure with fields to update from above
* `key` (string): Identifier for the model data to update

Returns <kbd><mark style="color:orange;">**boolean**</mark></kbd> - true if successful

Example:
```lua
local edit = {
    Health = 50,
    MaxHealth = 100,
    Whitelisted = true
}
edit_model_data(edit, "key_1")
```

#### remove_model_data
```lua
remove_model_data(key)
```
Removes existing model data for a specific key.

Parameters:
* `key` (string): Identifier for the model data to remove

Returns <kbd><mark style="color:orange;">**boolean**</mark></kbd> - true if successful

#### clear_model_data
```lua
clear_model_data()
```
Removes all model data.

Returns <kbd><mark style="color:orange;">**boolean**</mark></kbd> - true if successful

## Local Data Structure
Initializes and stores local player-related data from the Lua environment.

### Fields
* <kbd><mark style="color:red;">**userdata**</mark></kbd>`LocalPlayer` : Reference to the local player object
* <kbd><mark style="color:yellow;">**string**</mark></kbd>`Displayname` : Local player's visible name
* <kbd><mark style="color:yellow;">**string**</mark></kbd>`Username` : Local player's account username
* <kbd><mark style="color:blue;">**number**</mark></kbd>`Userid` : Unique ID for the local player (Roblox user ID)
* <kbd><mark style="color:red;">**userdata**</mark></kbd>`Character` : Reference to the local player's character model
* <kbd><mark style="color:purple;">**OPTIONAL**</mark></kbd> <kbd><mark style="color:red;">**userdata**</mark></kbd>`Team` : Team object the local player belongs to
* <kbd><mark style="color:red;">**userdata**</mark></kbd>`RootPart` : Primary part (e.g., HumanoidRootPart) of the local player
* <kbd><mark style="color:red;">**userdata**</mark></kbd>`LeftFoot` : LeftFoot part of the local character
* <kbd><mark style="color:red;">**userdata**</mark></kbd>`Head` : Head part of the local character
* <kbd><mark style="color:red;">**userdata**</mark></kbd>`LowerTorso` : LowerTorso part of the local character
* <kbd><mark style="color:red;">**userdata**</mark></kbd>`Tool` : Currently equipped tool or weapon, if any
* <kbd><mark style="color:red;">**userdata**</mark></kbd>`Humanoid` : Humanoid userdata controlling the character
* <kbd><mark style="color:purple;">**OPTIONAL**</mark></kbd> <kbd><mark style="color:blue;">**number**</mark></kbd>`Health` : Current health value
* <kbd><mark style="color:blue;">**number**</mark></kbd>`MaxHealth` : Maximum health value
* <kbd><mark style="color:blue;">**number**</mark></kbd>`RigType` : Rig type used (e.g., R6 = 0 or R15 = 1)

### Methods

#### override_local_data
```lua
override_local_data(data)
```
Overrides existing or creates local data for the local thread.

Parameters:
* `data` (table): Local data structure containing fields listed above

Returns <kbd><mark style="color:orange;">**boolean**</mark></kbd> - true if successful

Example:
```lua
local data = {
    LocalPlayer = Player,
    Username = "LocalUser",
    Displayname = "LocalDisplay",
    -- additional fields from above...
}
override_local_data(data)
```

#### clear_local_data
```lua
clear_local_data()
```
Removes all created local data.

Returns <kbd><mark style="color:orange;">**boolean**</mark></kbd> - true if successful
