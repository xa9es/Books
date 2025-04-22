# Gif

{% code overflow="wrap" %}
```lua
local Image = Drawing.new("Image")
Image.Url = "https://media4.giphy.com/media/v1.Y2lkPTc5MGI3NjExOGliNDQ2NzRrN2MxMmV3OHR4bnN6YzB0aDBmMDV4azAyMHdxOHJydiZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/5qdFqpRZPHHBlw7ZCv/giphy.gif"
Image.Visible = true
Image.zIndex = 1
Image.Gif = true
Image.Delay = 30
Image.Position = {400, 100}
Image.Size = {500, 500}
wait(20) -- yield for 20 seconds
Image:Remove()
```
{% endcode %}
