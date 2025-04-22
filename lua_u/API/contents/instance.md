---
description: Functions for working with instances and their properties
---

# Get

## GetValue
```lua
getvalue(userdata)
```
Returns the value property of the userdata. This could be a `string`, `number`, `table`, `boolean`, or `int`.
{% hint style="warning" %}
Class name must include "Value".
{% endhint %}

## GetName
```lua
getname(userdata)
```
Returns the name of the userdata `string`

## GetClassName
```lua
getclassname(userdata)
```
Returns the classname of the userdata `string`

## GetChildren
```lua
getchildren(userdata)
```
Returns an array containing all of the userdata direct children `table`

## GetDescendants
```lua
getdescendants(userdata)
```
Returns an array containing all children of the userdata and every child of those children `table`
{% hint style="warning" %}
This function is marked as [unsafe] in the documentation.
{% endhint %}

## GetParent
```lua
getparent(userdata)
```
Returns the parent of the userdata `userdata`

## FindFirstChild
```lua
findfirstchild(userdata, string)
```
Returns the first child of the userdata with the given name `userdata`

## FindFirstChildOfClass
```lua
findfirstchildofclass(userdata, string)
```
Returns the first child of the userdata whose classname is equal to the given classname `userdata`

## FindFirstAncestorOfClass
```lua
findfirstancestorofclass(userdata, string)
```
Returns the first ancestor of the userdata whose classname is equal to the given classname `userdata`

## FindFirstDescendant
```lua
findfirstdescendant(userdata, string)
```
Returns the first descendant found with the given name `userdata`

## FindFirstAncestor
```lua
findfirstancestor(userdata, string)
```
Returns the first ancestor of the userdata whose name is equal to the given name `userdata`

## WaitForChild
```lua
waitforchild(userdata, string, [timeout])
```
Returns the child of the userdata with the given name. If the child does not exist, it will pause the current thread until it does. If the timeout parameter is specified, this will time out after the specified number of seconds and return nil `userdata`

## IsAncestorOf
```lua
isancestorof(userdata, userdata)
```
Returns true if the first userdata is an ancestor of the given descendant (second userdata) `boolean`

## IsDescendantOf
```lua
isdescendantof(userdata, userdata)
```
Returns true if the first userdata is a descendant of the given ancestor (second userdata) `boolean`

# Set

## Destroy
```lua
destroy(userdata)
```
Sets the userdata parent to nil, effectively destroying it `void`