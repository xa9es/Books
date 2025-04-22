---
description: >-
  This primarily for storing character-related information, used for gameplay
  logic such as targeting, visualization, and status tracking.
---

# Model Data

## Add Model

Defines the structure for storing character-related information, used for gameplay logic such as targeting, visualization, and status tracking.

### Fields

* <kbd><mark style="color:yellow;">**string**<mark style="color:yellow;"></kbd>`Username` : The player's in-game username
* <kbd><mark style="color:yellow;">**string**<mark style="color:yellow;"></kbd>`Displayname` : The player's display name
* <kbd><mark style="color:blue;">**number**<mark style="color:blue;"></kbd>`Userid` : Unique player identifier (Roblox UserId)
* <kbd><mark style="color:red;">**userdata**<mark style="color:red;"></kbd>`Character` : Reference to the character model userdata
* <kbd><mark style="color:red;">**userdata**<mark style="color:red;"></kbd>`PrimaryPart` : The root/base part of the character (usually HumanoidRootPart)
* <kbd><mark style="color:red;">**userdata**<mark style="color:red;"></kbd>`Head` : Head part of the character
* <kbd><mark style="color:red;">**userdata**<mark style="color:red;"></kbd>`LeftLeg` : Left leg part
* <kbd><mark style="color:red;">**userdata**<mark style="color:red;"></kbd>`LeftArm` : Left arm part
* <kbd><mark style="color:red;">**userdata**<mark style="color:red;"></kbd>`RightLeg` : Right leg part
* <kbd><mark style="color:red;">**userdata**<mark style="color:red;"></kbd>`RightArm` : Right arm part
* <kbd><mark style="color:red;">**userdata**<mark style="color:red;"></kbd>`Torso` : Torso or central body part
* <kbd><mark style="color:blue;">**number**<mark style="color:blue;"></kbd>`BodyHeightScale` : Height scale multiplier for the character
* <kbd><mark style="color:blue;">**number**<mark style="color:blue;"></kbd>`RigType` : Rig type (e.g., "R6 = 0" or "R15 = 1")
* <kbd><mark style="color:orange;">**boolean**<mark style="color:orange;"></kbd>`Whitelisted` : Whether the player is excluded from hostile logic
* <kbd><mark style="color:orange;">**boolean**<mark style="color:orange;"></kbd>`Archenemies` : Designates a hostile player
* <kbd><mark style="color:red;">**userdata**<mark style="color:red;"></kbd>`Aimbot_Part` : Preferred target part for aimbot functionality
* <kbd><mark style="color:red;">**userdata**<mark style="color:red;"></kbd>`Aimbot_TP_Part` : Target part for aimbot teleportation (e.g., for mouse tp)
* <kbd><mark style="color:red;">**userdata**<mark style="color:red;"></kbd>`Triggerbot_Part` : Part used for triggerbot activation
* <kbd><mark style="color:blue;">**number**<mark style="color:blue;"></kbd>`Health` : Current health value of the character
* <kbd><mark style="color:blue;">**number**<mark style="color:blue;"></kbd>`MaxHealth` : Maximum health value
* <kbd><mark style="color:green;">**table**<mark style="color:green;"></kbd>`body_parts_data` : Table for specific body parts, typically used for chams & skeleton
  * Format: `{ name = "LowerTorso", part = userdata }`
* <kbd><mark style="color:green;">**table**<mark style="color:green;"></kbd>`full_body_data` : Table for all relevant body parts, typically used for closest and random body parts
  * Format: `{ name = "Head", part = userdata }`

### Methods

```lua
add_model_data(data, key)
```

Creates model data with a specific key that will be processed in the model thread.

Parameters:

* `data` (table): Model data structure containing fields listed above
* `key` (string): Unique identifier for this model data

Returns <kbd><mark style="color:orange;">**boolean**<mark style="color:orange;"></kbd> - true if successful

## Edit Model

Defines a partial data structure intended to update specific fields of an existing model data.

### Fields

* <kbd><mark style="color:blue;">**number**<mark style="color:blue;"></kbd>`RigType` : Rig type (e.g., R6 = 0, R15 = 1)
* <kbd><mark style="color:orange;">**boolean**<mark style="color:orange;"></kbd>`Whitelisted` : Whether the player is excluded from hostile checks
* <kbd><mark style="color:orange;">**boolean**<mark style="color:orange;"></kbd>`Archenemies` : Designates a hostile player
* <kbd><mark style="color:red;">**userdata**<mark style="color:red;"></kbd>`Aimbot_Part` : Target part for aimbot (usually the head)
* <kbd><mark style="color:red;">**userdata**<mark style="color:red;"></kbd>`Aimbot_TP_Part` : Target part for teleporting with aimbot (default: head) (mouse tp)
* <kbd><mark style="color:red;">**userdata**<mark style="color:red;"></kbd>`Triggerbot_Part` : Target part used by triggerbot
* <kbd><mark style="color:blue;">**number**<mark style="color:blue;"></kbd>`Health` : Updated current health
* <kbd><mark style="color:blue;">**number**<mark style="color:blue;"></kbd>`MaxHealth` : Updated max health capacity
* <kbd><mark style="color:blue;">**number**<mark style="color:blue;"></kbd>`BodyHeightScale` : Updated height scaling value

### Methods

```lua
edit_model_data(data, key)
```

Edits existing model data for a specific key.

Parameters:

* `data` (table): Partial model data structure with fields to update from above
* `key` (string): Identifier for the model data to update

Returns <kbd><mark style="color:orange;">**boolean**<mark style="color:orange;"></kbd> - true if successful

## Remove Model

```lua
remove_model_data(key)
```

Removes existing model data for a specific key.

Parameters:

* `key` (string): Identifier for the model data to remove

Returns <kbd><mark style="color:orange;">**boolean**<mark style="color:orange;"></kbd> - true if successful

## Clear Model

```lua
clear_model_data()
```

Removes all model data.

Returns <kbd><mark style="color:orange;">**boolean**<mark style="color:orange;"></kbd> - true if successful

## Local Model

Initializes and stores local player-related data from the Lua environment.

#### Fields

* <kbd><mark style="color:red;">**userdata**<mark style="color:red;"></kbd>`LocalPlayer` : Reference to the local player object
* <kbd><mark style="color:yellow;">**string**<mark style="color:yellow;"></kbd>`Displayname` : Local player's visible name
* <kbd><mark style="color:yellow;">**string**<mark style="color:yellow;"></kbd>`Username` : Local player's account username
* <kbd><mark style="color:blue;">**number**<mark style="color:blue;"></kbd>`Userid` : Unique ID for the local player (Roblox user ID)
* <kbd><mark style="color:red;">**userdata**<mark style="color:red;"></kbd>`Character` : Reference to the local player's character model
* <kbd><mark style="color:purple;">**OPTIONAL**<mark style="color:purple;"></kbd> <kbd><mark style="color:red;">**userdata**<mark style="color:red;"></kbd>`Team` : Team object the local player belongs to
* <kbd><mark style="color:red;">**userdata**<mark style="color:red;"></kbd>`RootPart` : Primary part (e.g., HumanoidRootPart) of the local player
* <kbd><mark style="color:red;">**userdata**<mark style="color:red;"></kbd>`LeftFoot` : LeftFoot part of the local character
* <kbd><mark style="color:red;">**userdata**<mark style="color:red;"></kbd>`Head` : Head part of the local character
* <kbd><mark style="color:red;">**userdata**<mark style="color:red;"></kbd>`LowerTorso` : LowerTorso part of the local character
* <kbd><mark style="color:red;">**userdata**<mark style="color:red;"></kbd>`Tool` : Currently equipped tool or weapon, if any
* <kbd><mark style="color:red;">**userdata**<mark style="color:red;"></kbd>`Humanoid` : Humanoid userdata controlling the character
* <kbd><mark style="color:purple;">**OPTIONAL**<mark style="color:purple;"></kbd> <kbd><mark style="color:blue;">**number**<mark style="color:blue;"></kbd>`Health` : Current health value
* <kbd><mark style="color:blue;">**number**<mark style="color:blue;"></kbd>`MaxHealth` : Maximum health value
* <kbd><mark style="color:blue;">**number**<mark style="color:blue;"></kbd>`RigType` : Rig type used (e.g., R6 = 0 or R15 = 1)

### Override Local Model

```lua
override_local_data(data)
```

Overrides existing or creates local data for the local thread.

Parameters:

* `data` (table): Local data structure containing fields listed above

Returns <kbd><mark style="color:orange;">**boolean**<mark style="color:orange;"></kbd> - true if successful

### Clear Local Model

```lua
clear_local_data()
```

Removes all created local data.

Returns <kbd><mark style="color:orange;">**boolean**<mark style="color:orange;"></kbd> - true if successful

## Examples

{% content-ref url="../getting_started/examples/Add Local Player To Model Cache.md" %}
[Add Local Player To Model Cache.md](<../getting_started/examples/Add Local Player To Model Cache.md>)
{% endcontent-ref %}
