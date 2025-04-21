# Basic Mouse Aimbot

{% hint style="warning" %}
These methods are partially 'deprecated', I strongly recommended use better functions  
{% endhint %}

# Roblox Lua
## Expontentional Style
```lua
function getclosetplayer()
    local mouse = getmouseposition()
    local closest_fov_distance = 100
    local closest_player = nil
    local players = game.Players:GetChildren()
    local camera = workspace.CurrentCamera

    local l_plr = game.Players.localPlayer.Character
    local l_plr_root = l_plr:FindFirstChild("HumanoidRootPart")

    for _, player in ipairs(players) do
        local character = player.Character
        if not character then return end

        local head = character:FindFirstChild("Head")
        if not head then return end

        local head_position = head.CFrame.Position
        local wrld_to_screen = camera:WorldToScreenPoint(head_position)
        local distance = math.sqrt((wrld_to_screen.x - mouse.x)^2 + (wrld_to_screen.y - mouse.y)^2)

        if distance < closest_fov_distance then
            closest_fov_distance = distance
            closest_player = player
        end
    end

    return closest_player
end

function on_update()
    local camera = workspace.CurrentCamera
    local mouse_pos = getmouseposition()
    local closest_player = getclosetplayer()
    if not closest_player then return end
    local head = closest_player.Character:FindFirstChild("Head")
    if not head then return end

    local head_position = head.CFrame.Position
    local wrld_to_screen, onScreen = camera:WorldToScreenPoint(head_position)

    if not onScreen then return end

    local point_to = {wrld_to_screen.x, wrld_to_screen.y}
    local speed = 0.5
    local result = smoothmouse_exponential({mouse_pos.x, mouse_pos.y}, point_to, speed)

    mousemoverel(result.x, result.y)
end

spawn(function()
    while wait() do
        on_update()
    end
end)
```

## Linear Style
```lua
function getclosetplayer()
    local mouse = getmouseposition()
    local closest_fov_distance = 100
    local closest_player = nil
    local players = get(Game)
    local camera = workspace.CurrentCamera

    local l_plr = game.Players.localPlayer.Character
    local l_plr_root = l_plr:FindFirstChild("HumanoidRootPart")

    for _, player in ipairs(players) do
        local character = player.Character
        if not character then return end

        local head = character:FindFirstChild("Head")
        if not head then return end

        local head_position = head.CFrame.Position
        local wrld_to_screen = camera:WorldToScreenPoint(head_position)
        local distance = math.sqrt((wrld_to_screen.x - mouse.x)^2 + (wrld_to_screen.y - mouse.y)^2)

        if distance < closest_fov_distance then
            closest_fov_distance = distance
            closest_player = player
        end
    end

    return closest_player
end

function on_update()
    local camera = workspace.CurrentCamera
    local mouse_pos = getmouseposition()
    local closest_player = getclosetplayer()
    if not closest_player then return end
    local head = closest_player.Character:FindFirstChild("Head")
    if not head then return end

    local head_position = head.CFrame.Position
    local wrld_to_screen, onScreen = camera:WorldToScreenPoint(head_position)

    if not onScreen then return end

    local point_to = {wrld_to_screen.x, wrld_to_screen.y}
    local speed = 0.5
    local result = smoothmouse_exponential({mouse_pos.x, mouse_pos.y}, point_to, speed)

    mousemoverel(result.x, result.y)
    print(result.x, result.y)
end

spawn(function()
    while wait() do
        on_update()
    end
end)
```

# LuaU

## Expontential Style
```lua
function getclosetplayer()
    local mouse = getmouseposition()
    local closest_fov_distance = 100
    local closest_player = nil
    local players = findfirstchild(Game, "Players")

    local l_plr = getlocalplayer()
    local l_plr_root = findfirstchild(l_plr, "HumanoidRootPart")

    for _, player in ipairs(getchildren(players)) do
        local character = getcharacter(player)
        if not character then return end

        local head = findfirstchild(character, "Head")
        if not head then return end

        local head_position = getposition(head)
        local wrld_to_screen = worldtoscreenpoint({head_position.x, head_position.y, head_position.z})
        local distance = math.sqrt((wrld_to_screen.x - mouse.x)^2 + (wrld_to_screen.y - mouse.y)^2)

        if distance < closest_fov_distance then
            closest_fov_distance = distance
            closest_player = player
        end
    end

    return closest_player
end

function on_update()
    local mouse_pos = getmouseposition()
    local closest_player = getclosetplayer()
    if not closest_player then return end
    local head = findfirstchild(getcharacter(closest_player), "Head")
    if not head then return end

    local head_position = getposition(head)
    local wrld_to_screen, onScreen = worldtoscreenpoint({head_position.x, head_position.y, head_position.z})

    if not onScreen then return end

    local point_to = {wrld_to_screen.x, wrld_to_screen.y}
    local speed = 0.5
    local result = smoothmouse_exponential({mouse_pos.x, mouse_pos.y}, point_to, speed)

    mousemoverel(result.x, result.y)
end

spawn(function()
    while wait() do
        on_update()
    end
end)
```

## Linear Style
```lua
function getclosetplayer()
    local mouse = getmouseposition()
    local closest_fov_distance = 100
    local closest_player = nil
    local players = findfirstchild(Game, "Players")

    local l_plr = getlocalplayer()
    local l_plr_root = findfirstchild(l_plr, "HumanoidRootPart")

    for _, player in ipairs(getchildren(players)) do
        local character = getcharacter(player)
        if not character then return end

        local head = findfirstchild(character, "Head")
        if not head then return end

        local head_position = getposition(head)
        local wrld_to_screen = worldtoscreenpoint({head_position.x, head_position.y, head_position.z})
        local distance = math.sqrt((wrld_to_screen.x - mouse.x)^2 + (wrld_to_screen.y - mouse.y)^2)

        if distance < closest_fov_distance then
            closest_fov_distance = distance
            closest_player = player
        end
    end

    return closest_player
end

function on_update()
    local mouse_pos = getmouseposition()
    local closest_player = getclosetplayer()
    if not closest_player then return end
    local head = findfirstchild(getcharacter(closest_player), "Head")
    if not head then return end

    local head_position = getposition(head)
    local wrld_to_screen, onScreen = worldtoscreenpoint({head_position.x, head_position.y, head_position.z})

    if not onScreen then return end

    local point_to = {wrld_to_screen.x, wrld_to_screen.y}
    local speed = 0.5
    local result = smoothmouse_linear({mouse_pos.x, mouse_pos.y}, point_to, speed)

    mousemoverel(result.x, result.y)
end

spawn(function()
    while wait() do
        on_update()
    end
end)
```