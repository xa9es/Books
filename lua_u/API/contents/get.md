# Get

# Methods
## Value
```lua
getvalue(userdata)
```
Returns the value property of the userdata. This could be a `string` or `number`, `table`, `boolean`, `int`.
{% hint style="warning" %}
Class name must include "Value".
{% endhint %}

## Find First Child
```lua
findfirstchild(userdata, string)
```
Returns the first child of the userdata with the given name `userdata`

## Find First Child Of Class
```lua
findfirstchildofclass(userdata, string)
```
Returns the first child of the userdata whose classname is equal to the given classname `userdata`