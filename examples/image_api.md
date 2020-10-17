# ImageRender

> Author: [@Neverlose](https://github.com/neverlosecc)
>
> Name: `Image render example`
>
> Description: `Image render example`


```lua
local size = Vector2.new(500, 120)
local pos = Vector2.new(100, 100)
local pos2 = Vector2.new(600, 100)

local url = "https://neverlose.cc/static/assets/img/logo.png"
local path = "D:\\downloads\\logo.png"

local bytes = Http.Get(url)

local image_from_bytes = g_Render.LoadImage(bytes, size)
local image_from_disk = g_Render.LoadImageFromFile(path, size)


cheat.RegisterCallback("draw", function()
    g_Render.Image(image_from_bytes, pos, size)
	g_Render.Image(image_from_disk, pos2, size)
end)
```
