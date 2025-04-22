# Add Model Data To Severe

<div align="center" data-full-width="false"><figure><img src="../../.gitbook/assets/plasrv_DGnpEKbl2G.gif" alt=""><figcaption><p>Add Local Player to severe</p></figcaption></figure></div>

{% tabs %}
{% tab title="Roblox Lua" %}
{% code overflow="wrap" %}
```lua
local localPlayer = game.Players.localPlayer.Character

function Create_Model_Data(model)
    local data = {
        Username = model.Name,
        Displayname = model.Name,
        Userid = 18287,
        Character = model.Data,
        PrimaryPart = model.PrimaryPart.Data or model:FindFirstChild("HumanoidRootPart").Data,
        Humanoid = model:FindFirstChild("Humanoid").Data,
        Head = model:FindFirstChild("Head").Data,
        LeftLeg = model:FindFirstChild("Left Leg").Data,
        LeftArm = model:FindFirstChild("Left Arm").Data,
        RightArm = model:FindFirstChild("Right Arm").Data,
        RightLeg = model:FindFirstChild("Right Leg").Data,
        Torso = model:FindFirstChild("Torso").Data,
        BodyHeightScale = 1,
        RigType = 0,
        Whitelisted = false,
        Archenemies = false,
        Aimbot_Part = model:FindFirstChild("Head").Data,
        Aimbot_TP_Part = model:FindFirstChild("Head").Data,
        Triggerbot_Part = model:FindFirstChild("Head").Data,
        Health = model:FindFirstChild("Humanoid") and model.Humanoid.Health or 100,
        MaxHealth = model:FindFirstChild("Humanoid") and model.Humanoid.MaxHealth or 100,
    }
    return data
end

local data = Create_Model_Data(localPlayer)
clear_model_data()
add_model_data(data, "key_1")
```
{% endcode %}
{% endtab %}

{% tab title="LuaU" %}
{% code fullWidth="false" %}
```lua
local localPlayer = getlocalplayer()

function Create_Model_Data(model)
    local data = {
        Username = getname(model),
        Displayname = getdisplayname(model),
        Userid = getuserid(model),
        Character = getcharacter(model),
        PrimaryPart = getprimarypart(getcharacter(model)) or findfirstchild(getcharacter(model), "HumanoidRootPart"),
        Humanoid = findfirstchild(getcharacter(model), "Humanoid"),
        Head = findfirstchild(getcharacter(model), "Head"),
        LeftLeg = findfirstchild(getcharacter(model), "Left Leg"),
        LeftArm = findfirstchild(getcharacter(model), "Left Arm"),
        RightArm = findfirstchild(getcharacter(model), "Right Arm"),
        RightLeg = findfirstchild(getcharacter(model), "Right Leg"),
        Torso = findfirstchild(getcharacter(model), "Torso"),
        BodyHeightScale = 1,
        RigType = 0,
        Whitelisted = false,
        Archenemies = false,
        Aimbot_Part = findfirstchild(getcharacter(model), "Head"),
        Aimbot_TP_Part = findfirstchild(getcharacter(model), "Head"),
        Triggerbot_Part = findfirstchild(getcharacter(model), "Head"),
        Health = findfirstchild(getcharacter(model), "Humanoid") and gethealth(findfirstchild(getcharacter(model), "Humanoid")) or 100,
        MaxHealth = findfirstchild(getcharacter(model), "Humanoid") and getmaxhealth(findfirstchild(getcharacter(model), "Humanoid")) or 100,
    }
    return data
end

local data = Create_Model_Data(localPlayer)
clear_model_data()
add_model_data(data, "key_1")
```
{% endcode %}
{% endtab %}
{% endtabs %}
