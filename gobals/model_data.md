---
description: This primarily for storing character-related information, used for gameplay logic such as targeting, visualization, and status tracking.
---

# Model Data Structures

## Model Data Structure
Defines the structure for storing character-related information, used for gameplay logic such as targeting, visualization, and status tracking.

### Fields
- `Username` (string): The player's in-game username
- `Displayname` (string): The player's display name
- `Userid` (number): Unique player identifier (Roblox UserId)
- `Character` (Instance): Reference to the character model instance
- `PrimaryPart` (Instance): The root/base part of the character (usually HumanoidRootPart)
- `Head` (Instance): Head part of the character
- `LeftLeg` (Instance): Left leg part
- `LeftArm` (Instance): Left arm part
- `RightLeg` (Instance): Right leg part
- `RightArm` (Instance): Right arm part
- `Torso` (Instance): Torso or central body part
- `BodyHeightScale` (number): Height scale multiplier for the character
- `RigType` (number): Rig type (e.g., "R6 = 0" or "R15 = 1")
- `Whitelisted` (boolean): Whether the player is excluded from hostile logic
- `Archenemies` (boolean): Designates a hostile player
- `Aimbot_Part` (Instance): Preferred target part for aimbot functionality
- `Aimbot_TP_Part` (Instance): Target part for aimbot teleportation (e.g., for mouse tp)
- `Triggerbot_Part` (Instance): Part used for triggerbot activation
- `Health` (number): Current health value of the character
- `MaxHealth` (number): Maximum health value
- `body_parts_data` (table): Table for specific body parts, typically used for chams & skeleton
  - Format: `{ name = "LowerTorso", part = userdata }`
- `full_body_data` (table): Table for all relevant body parts, typically used for closest and random body parts
  - Format: `{ name = "Head", part = userdata }`

## Model Edit Structure
Defines a partial data structure intended to update specific fields of an existing model data.

### Fields
- `RigType` (number): Rig type (e.g., R6 = 0, R15 = 1)
- `Whitelisted` (boolean): Whether the player is excluded from hostile checks
- `Archenemies` (boolean): Designates a hostile player
- `Aimbot_Part` (Instance): Target part for aimbot (usually the head)
- `Aimbot_TP_Part` (Instance): Target part for teleporting with aimbot (default: head) (mouse tp)
- `Triggerbot_Part` (Instance): Target part used by triggerbot
- `Health` (number): Updated current health
- `MaxHealth` (number): Updated max health capacity
- `BodyHeightScale` (number): Updated height scaling value

## Local Data Structure
Initializes and stores local player-related data from the Lua environment into the internal `Data` structure.

### Fields
- `LocalPlayer` (userdata): Reference to the local player object
- `Displayname` (string): Local player's visible name
- `Username` (string): Local player's account username
- `Userid` (number): Unique ID for the local player (Roblox user ID)
- `Character` (userdata): Reference to the local player's character model
- `Team` (userdata, optional): Team object the local player belongs to
- `RootPart` (userdata): Primary part (e.g., HumanoidRootPart) of the local player
- `LeftFoot` (userdata): LeftFoot part of the local character
- `Head` (userdata): Head part of the local character
- `LowerTorso` (userdata): LowerTorso part of the local character
- `Tool` (userdata, optional): Currently equipped tool or weapon, if any
- `Humanoid` (userdata): Humanoid instance controlling the character
- `Health` (number, optional): Current health value
- `MaxHealth` (number, optional): Maximum health value
- `RigType` (number): Rig type used (e.g., R6 = 0 or R15 = 1)

# Methods

## add_model_data
```lua
add_model_data(data, key)
```
Creates model data with a specific key that will be processed in the model thread.

Parameters:
- `data` (table): Model data structure 
- `key` (string): Unique identifier for this model data

Returns `boolean` - true if successful

### Example
```lua
local data = {
    Username = "Player1",
    Displayname = "CoolPlayer",
    Userid = 123456,
    Character = workspace.Player1.Character,
    PrimaryPart = workspace.Player1.Character.HumanoidRootPart,
    -- additional fields...
}

add_model_data(data, "key_1")
```

## edit_model_data
```lua
edit_model_data(data, key)
```
Edits existing model data for a specific key.

Parameters:
- `data` (table): Partial model data structure with fields to update
- `key` (string): Identifier for the model data to update

Returns `boolean` - true if successful

### Example
```lua
local edit = {
    Health = 50,
    MaxHealth = 100,
    Whitelisted = true
}

edit_model_data(edit, "key_1")
```

## remove_model_data
```lua
remove_model_data(key)
```
Removes existing model data for a specific key.

Parameters:
- `key` (string): Identifier for the model data to remove

Returns `boolean` - true if successful

## clear_model_data
```lua
clear_model_data()
```
Removes all model data.

Returns `boolean` - true if successful

## override_local_data
```lua
override_local_data(data)
```
Overrides existing or creates local data for the local thread.

Parameters:
- `data` (table): Local data structure

Returns `boolean` - true if successful

### Example
```lua
local data = {
    LocalPlayer = Player,
    Username = "LocalUser",
    Displayname = "LocalDisplay",
    -- additional fields...
}

override_local_data(data)
```

## clear_local_data
```lua
clear_local_data()
```
Removes all created local data.

Returns `boolean` - true if successful 