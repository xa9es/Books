# Examples

## Text Example
```lua
local text = Drawing.new("Text")
text.Text = "severe drawing library!"
text.Visible = true
text.zIndex = 1
text.Position = {10, 10}
text.Color = {255, 255, 255}
text.Size = 15
wait(5) -- Display for 5 seconds
text:Remove()
```