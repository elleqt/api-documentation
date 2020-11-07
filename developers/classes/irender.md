# IRender

{% hint style="info" %}
Instance of `IRender` is `g_Render`
{% endhint %}

{% hint style="warning" %}
IRender functions can be called **only** from `draw` or `esp` [callbacks](../other/callbacks.md)
{% endhint %}

## Functions

## Line

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| pos | Vector2 | Start 2D Position on the screen |
| pos2 | Vector2 | End 2D Position on the screen |
| clr | Color | Line's color |

```lua
g_Render.Line(Vector2.new(0, 0), Vector2.new(100, 100), Color.new(1.0, 1.0, 1.0, 1.0))
```

## Box

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| pos | Vector2 | Start 2D Position on the screen |
| pos2 | Vector2 | End 2D Position on the screen |
| clr | Color | Box's color |

```lua
g_Render.Box(Vector2.new(0, 0), Vector2.new(100, 100), Color.new(1.0, 1.0, 1.0, 1.0))
```

## BoxFilled

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| pos | Vector2 | Start 2D Position on the screen |
| pos2 | Vector2 | End 2D Position on the screen |
| clr | Color | FilledBox's color |

```lua
g_Render.BoxFilled(Vector2.new(0, 0), Vector2.new(100, 100), Color.new(1.0, 1.0, 1.0, 1.0))
```

## GradientBoxFilled

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| pos | Vector2 | Start 2D Position on the screen |
| pos2 | Vector2 | End 2D Position on the screen |
| clr | Color | GradientBoxFilled's color 1 |
| clr2 | Color | GradientBoxFilled's color 2 |
| clr3 | Color | GradientBoxFilled's color 3 |
| clr4 | Color | GradientBoxFilled's color 4 |

```lua
g_Render.GradientBoxFilled(Vector2.new(100, 100), Vector2.new(300, 300), Color.new(0, 0, 0, 1), Color.new(0, 0, 0, 1), Color.new(1, 1, 1, 1), Color.new(1, 1, 1, 1))
```

## Circle

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| pos | Vector2 | Start 2D Position on the screen |
| rad | float | Circle radius |
| pnts | int | Circle points |
| clr | Color | Circle's color |

```lua
g_Render.Circle(Vector2.new(100, 500), 1.0, 58, Color.new(1.0, 1.0, 1.0, 1.0))
```

## CircleFilled

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| pos | Vector2 | Start 2D Position on the screen |
| rad | float | Circle radius |
| pnts | int | Circle points |
| clr | Color | Circle's color |

```lua
g_Render.CircleFilled(Vector2.new(100, 500), 1.0, 58, Color.new(1.0, 1.0, 1.0, 1.0))
```

## Text

### Parameters:

| Name | Type | Description | Required |
| :--- | :--- | :--- | :--- |
| text | string | Text | + |
| pos | Vector2 | Text start position | + |
| clr | Color | Text color | + |
| size | int | Text's size | + |
| font | Font\* | Text's font | - |
| outline | bool | Text outline | - |

```lua
g_Render.Text("Hello world, it's me", Vector2.new(150, 150), Color.new(1.0, 1.0, 1.0, 1.0), 16)
local font = g_Render.InitFont("Arial", 16)
g_Render.Text("Hello world, it's me", Vector2.new(250, 250), Color.new(1.0, 1.0, 1.0, 1.0), 16, font)
```

## CalcTextSize

### Parameters:

| Name | Type | Description | Required |
| :--- | :--- | :--- | :--- |
| text | string | Text | + |
| size | int | Text's size | + |
| font | Font\* | Text's font | - |

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| size | Vector2 | Text sizes |

```lua
local text_size = g_Render.CalcTextSize("Hello world, it's me", 16)
print("X size: "..tostring(text_size.x).." | Y size: "..tostring(text_size.y))

local font = g_Render.InitFont("Arial", 16)
text_size = _Render.CalcTextSize("Hello world, it's me", 16, font)
print("X size: "..tostring(text_size.x).." | Y size: "..tostring(text_size.y))
```

## ScreenPosition

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| pos | Vector | 3D Position |

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| pos | Vector2 | 2D Position on the screen |

```lua
local screen_pos = g_Render.ScreenPosition(Vector.new(0, 0, 0))
```

## Circle3D

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| pos | Vector | 3D world position |
| pnts | int | Points |
| rad | float | Radius |
| clr | Color | Circle color |

```lua
g_Render.Circle3D(Vector.new(0, 0), 58, 10.0, Color.new(1.0, 1.0, 1.0))
```

## CircleFilled3D

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| pos | Vector | 3D world position |
| pnts | int | Points |
| rad | float | Radius |
| clr | Color | Circle color |

```lua
g_Render.CircleFilled3D(Vector.new(0, 0), 58, 10.0, Color.new(1.0, 1.0, 1.0))
```

## CylinderFilled3D

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| pos | Vector | 3D world position |
| pnts | int | Points |
| rad | float | Radius |
| height | float | Cylinder's height |
| clr | Color | Circle color |

```lua
g_Render.CylinderFilled3D(Vector.new(0, 0), 58, 10.0, 30.0, Color.new(1.0, 1.0, 1.0))
```

## InitFont

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| name | string | Font name |
| size | int | Font size |

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| font | Font\* | Created font |

```lua
local font = g_Render.InitFont("Arial", 16)
g_Render.Text("Hello world, it's me", Vector2.new(250, 250), Color.new(1.0, 1.0, 1.0, 1.0), 16, font)
```

## WeaponIcon

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| def\_index | int | Weapon definition index |
| pos | Vector2 | 2D Position on screen |
| clr | Color | Icon color |
| size | int | Icon size |

```lua
g_Render.WeaponIcon(7, Vector2.new(100, 100), Color.new(1.0, 1.0, 1.0), 16)
```

## CalcWeaponIconSize

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| def\_index | int | Weapon definition index |
| size | int | Icon size |

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| size | Vector2 | Icon sizes |

```lua
local icon_size = g_Render.CalcWeaponIconSize(7, 16)
print("X size: "..tostring(icon_size.x).." | Y size: "..tostring(icon_size.y))
```

