---
description: Functions for working with instances and their properties
---

# Instance

## Get

### GetValue

```lua
instance.Value
```

Returns the value property of a value object. This could be a `string`, `number`, `table`, `boolean`, or `int`.

{% hint style="warning" %}
Class name must include "Value"
{% endhint %}

### GetChildren

```lua
instance:GetChildren()
```

Returns an array containing all of the instance's direct children `table`

### GetDescendants

```lua
instance:GetDescendants()
```

Returns an array containing all children of the instance and every child of those children `table`

### FindFirstChild

```lua
instance:FindFirstChild(name)
```

Returns the first child of the instance with the given name `table`

### FindFirstChildOfClass

```lua
instance:FindFirstChildOfClass(className)
```

Returns the first child of the instance whose classname is equal to the given classname `table`

### FindFirstAncestorOfClass

```lua
instance:FindFirstAncestorOfClass(className)
```

Returns the first ancestor of the instance whose classname is equal to the given classname `table`

### IsAncestorOf

```lua
instance:IsAncestorOf(descendant)
```

Returns true if the instance is an ancestor of the given descendant `boolean`

### IsDescendantOf

```lua
instance:IsDescendantOf(ancestor)
```

Returns true if the instance is a descendant of the given ancestor `boolean`

### WaitForChild

{% hint style="warning" %}
Not recommended
{% endhint %}

```lua
instance:WaitForChild(name, [timeout])
```

Returns the child of the instance with the given name. If the child does not exist, it will pause the current thread until it does. If the timeout parameter is specified, this will time out after the specified number of seconds and return nil `table`

## Set

### SetValue

```lua
valueObject:SetValue(value)
```

Sets the value property of a value object. The class name must include "Value" and the provided value must match the expected type `void`

### Destroy

```lua
instance:Destroy()
```

Sets the instance's parent to nil, effectively destroying it `void`
