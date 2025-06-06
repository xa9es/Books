---
description: Functions for working with positions, vectors, and CFrames
---

# Transform

## Get

### GetPosition

```lua
instance.CFrame.Position
```

Returns the position of the part or camera `Vector3`

### GetCFrame

```lua
instance.CFrame
```

Returns the CFrame of the part or camera `CFrame`

### GetLookVector

```lua
instance.CFrame.LookVector
```

Returns the look vector of the part or camera `Vector3`

### GetRightVector

```lua
instance.CFrame.RightVector
```

Returns the right vector of the part or camera `Vector3`

### GetUpVector

```lua
instance.CFrame.UpVector
```

Returns the up vector of the part or camera `Vector3`

### GetSize

```lua
instance.Size
```

Returns the size of the part `Vector3`

### WorldToScreenPoint

```lua
camera:WorldToScreenPoint(Vector3.new())
```

Returns the screen coordinates of the Vector3 and whether this point is within the bounds of the screen `Vector2, boolean`

## Set

### SetCFrame

```lua
instance.CFrame = CFrame.new()
```

Sets the CFrame of the instance `void`

### SetPosition

```lua
instance.Position = Vector3.new()
```

Sets the position of the instance `void`

### SetVelocity

```lua
instance.Velocity = Vector3.new()
```

Sets the velocity of the instance `void`
