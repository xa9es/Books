---
description: Functions for working with positions, vectors, and CFrames
---

# Get

## GetPosition
```lua
getposition(userdata)
```
Returns the position of the given part or camera `Vector3 {x, y, z}`

## GetLookVector
```lua
getlookvector(userdata)
```
Returns the lookvector of the given part or camera `Vector3 {x, y, z}`

## GetRightVector
```lua
getrightvector(userdata)
```
Returns the rightvector of the given part or camera `Vector3 {x, y, z}`

## GetUpVector
```lua
getupvector(userdata)
```
Returns the upvector of the given part or camera `Vector3 {x, y, z}`

## GetSize
```lua
getsize(userdata)
```
Returns the size of the given part `Vector3 {x, y, z}`

## GetVelocity
```lua
getvelocity(userdata)
```
Returns the velocity of the given part `Vector3 {x, y, z}`

## GetCFrame
```lua
getcframe(userdata)
```
Returns the CFrame of the given part or camera `CFrame {lookvector, upvector, rightvector, position}`

## LerpVector3
```lua
lerpvector3(vector3_1, vector3_2, alpha)
```
Returns a vector3 interpolated between vector3_1 and vector3_2 by the fraction alpha `Vector3 {x, y, z}`

## LerpCFrame
```lua
lerpcframe(cframe_1, cframe_2, alpha)
```
Returns a CFrame interpolated between cframe_1 and cframe_2 by the fraction alpha `CFrame {lookvector, upvector, rightvector, position}`

## CFrameLookAt
```lua
cframelookat(cframe, vector3)
```
Returns a new CFrame with the position of cframe and facing towards vector3 `CFrame {lookvector, upvector, rightvector, position}`

## WorldToScreenPoint
```lua
worldtoscreenpoint(vector3)
```
Returns the screen coordinates of the vector3 and whether this point is within the bounds of the screen `{x, y}, boolean`

# Set

## SetCFrame
```lua
setcframe(userdata, cframe)
```
Sets the CFrame of the userdata to the given CFrame `void`

## SetLookVector
```lua
setlookvector(userdata, vector3)
```
Sets the lookvector of the userdata to the given vector3 `void`

## SetUpVector
```lua
setupvector(userdata, vector3)
```
Sets the upvector of the userdata to the given vector3 `void`

## SetRightVector
```lua
setrightvector(userdata, vector3)
```
Sets the rightvector of the userdata to the given vector3 `void`

## SetPosition
```lua
setposition(userdata, vector3)
```
Sets the position of the userdata to the given vector3 `void`

## SetVelocity
```lua
setvelocity(userdata, vector3)
```
Sets the velocity of the userdata to the given vector3 `void`