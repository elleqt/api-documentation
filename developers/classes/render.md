# Render

{% hint style="info" %} Instance of `Render` is `g_Render` {% endhint %}

## Functions

## Line

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| start | Vector2 | Startpoint of the line |
| end | Vector2 | Endpoint of the line |
| clr | Color | Linecolor |

### Usage:
```lua
g_Render:Line(Vector2.new(0.0, 0.0), Vector2.new(5.0, 6.0), Color.new(1.0, 1.0, 1.0, 1.0))
```

## PolyLine

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| clr | Color | Line color |
| vec | Vector | Variadic vector |

### Usage:
```lua

```

## PolyFilled

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| clr | Color | Line color |
| vec | Vector | Variadic vector |

### Usage:
```lua

```

## Box

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| start | Vector2 | Startpoint of the box |
| end | Vector2 | Endpoint of the box |
| clr | Color | Boxcolor |

### Usage:
```lua
g_Render:Box(Vector2.new(0.0, 0.0), Vector2.new(4.0, 5.0), Color.new(1.0, 1.0, 1.0, 1.0))
```

## BoxFilled

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| start | Vector2 | Startpoint of the box |
| end | Vector2 | Endpoint of the box |
| clr | Color | Boxcolor |

### Usage:
```lua
g_Render:BoxFilled(Vector2.new(0.0, 0.0), Vector2.new(4.0, 5.0), Color.new(1.0, 1.0, 1.0, 1.0))
```

## Circle

### Parameters:

| Name | Type | Description | Required |
| :--- | :--- | :--- | :--- |
| pos | Vector2 | Center of the circle | + |
| rad | float | Radius | + |
| seg | int | Amount of segments | + |
| clr | Color | Circlecolor | + |
| th  | float | Circle thickness | - |

### Usage:
```lua
g_Render:Circle(Vector2.new(0.0, 0.0), 2.0, 30, Color.new(1.0, 1.0, 1.0, 1.0))
```

## CircleFilled

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| pos | Vector2 | Center of the circle |
| rad | float | Radius |
| seg | int | Amount of segments |
| clr | Color | Circlecolor |

### Usage:
```lua
g_Render:CircleFilled(Vector2.new(0.0, 0.0), 2.0, 30, Color.new(1.0, 1.0, 1.0, 1.0))
```


## CirclePart

### Parameters:

| Name | Type | Description | Required |
| :--- | :--- | :--- | :--- |
| pos | Vector2 | Center of the circle | + |
| rad | float | Radius | + |
| seg | int | Amount of segments | + |
| clr | Color | Circlecolor | + |
| start | float | First Radian | + |
| end | float | Last Radian | + |
| th | float | Thickness | - |

### Usage:
```lua
g_Render:CirclePart(Vector2.new(0.0, 0.0), 2.0, 50, Color.new(1.0, 1.0, 1.0, 1.0), 1.0, 40.0, 2.0)
```

## Text

### Parameters:

| Name | Type | Description | Required |
| :--- | :--- | :--- | :--- |
| text | string | Text | + |
| pos | Vector2 | Text position | + |
| clr | Color | Textcolor | + |
| size | int | Textsize | + |
| font | Font* | Text font | - |
| out | bool | Text outline | - |

### Usage:
```lua
g_Render:Text("Anarchist is cute", Vector2.new(0.0, 0.0), Color.new(1.0, 1.0, 1.0, 1.0), 20)
```

## WeaponIcon

### Parameters:

| Name | Type | Description | Required |
| :--- | :--- | :--- | :--- |
| index | int | Weapon index | + |
| pos | Vector2 | Icon position | + |
| clr | Color | Icon color | + |
| size | int | Icon size | + |
| out | bool | Icon outline | - |

### Usage:
```lua
g_Render:WeaponIcon(7, Vector2.new(100, 100), Color.new(1.0, 1.0, 1.0), 16)
```

## CalcTextSize

### Parameters:

| Name | Type | Description | Required |
| :--- | :--- | :--- | :--- |
| text | string | Text | + |
| size | int | Textsize | + |
| font | Font* | Text font | - |


### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| size | Vector2 | Textsize |

### Usage:
```lua
local text_size = g_Render:CalcTextSize("Hello world, it's me", 16)
print("X size: "..tostring(text_size.x).." | Y size: "..tostring(text_size.y))

local font = g_Render:InitFont("Arial", 16)
text_size = g_Render:CalcTextSize("Hello world, it's me", 16, font)
print("X size: "..tostring(text_size.x).." | Y size: "..tostring(text_size.y))
```

## CalcWeaponIconSize

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| index | int | Weapon index |
| size | int | Icon size |

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| size | Vector2 | Iconsize |

### Usage:
```lua
local icon_size = g_Render:CalcWeaponIconSize(7, 16)
print("X size: "..tostring(icon_size.x).." | Y size: "..tostring(icon_size.y))
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
| font | Font* | Created Font |

### Usage:
```lua
local font = g_Render:InitFont("Arial", 16)
g_Render:Text("Hello world, it's me", Vector2.new(250, 250), Color.new(1.0, 1.0, 1.0, 1.0), 16, font)
```

## ScreenPosition

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| vec | Vector | 3-dimensional position |

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| vec | Vector2 | 2-dimensional screen position |

### Usage:
```lua
local screen_pos = g_Render:ScreenPosition(Vector.new(0, 0, 0))
```

## Circle3D

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| pos | Vector | 3-dimensional position |
| seg | int | Amount of segments |
| rad | float | Radius |
| clr | Color | Circle color |

### Usage:
```lua
g_Render:Circle3D(Vector.new(0, 0, 0), 58, 10.0, Color.new(1.0, 1.0, 1.0))
```

## Circle3DFilled

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| pos | Vector | 3-dimensional position |
| seg | int | Amount of segments |
| rad | float | Radius |
| clr | Color | Circle color |

### Usage:
```lua
g_Render:CircleFilled3D(Vector.new(0, 0, 0), 58, 10.0, Color.new(1.0, 1.0, 1.0))
```

## Cylinder3DFilled

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| pos | Vector | 3-dimensional position |
| seg | int | Amount of segments |
| rad | float | Radius |
| height | float | Cylinder height |
| clr | Color | Cylinder color |

### Usage:
```lua
g_Render:CylinderFilled3D(Vector.new(0, 0, 0), 58, 10.0, 30.0, Color.new(1.0, 1.0, 1.0))
```

## GradientBoxFilled

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| start | Vector2 | Beginning of the box |
| end | Vector2 | End of the box |
| t_l | Color | Color top left |
| t_r | Color | Color top right |
| b_l | Color | Color bottom left |
| b_r | Color | Color bottom right |

### Usage:
```lua
g_Render:GradientBoxFilled(Vector2.new(100, 100), Vector2.new(300, 300), Color.new(0, 0, 0, 1), Color.new(0, 0, 0, 1), Color.new(1, 1, 1, 1), Color.new(1, 1, 1, 1))
```

## Image

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
|  |  |  |
|  |  |  |
|  |  |  |

### Usage:
```lua

```

## LoadImage

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
|  |  |  |
|  |  |  |
|  |  |  |

### Usage:
```lua

```

## LoadImageFromFile

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
|  |  |  |
|  |  |  |
|  |  |  |

### Usage:
```lua

```

## GetMenuPos

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| vec | Vector2 | Menu position |

### Usage:
```lua
local menu_pos = g_Render:GetMenuPos()
print(menu_pos.x)
```

## GetMenuSize

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| vec | Vector2 | Menu size |

### Usage:
```lua
local menu_sz = g_Render:GetMenuSize()
print(menu_sz.y)
```
