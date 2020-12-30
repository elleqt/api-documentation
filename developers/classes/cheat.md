# Cheat

{% hint style="info" %}
Instance of `Cheat` is `cheat`
{% endhint %}

## ESP API

{% hint style="info" %}
You can create your own ESP elements. More info can be found [here](../other/espapi.md).
{% endhint %}

## Menu API

{% hint style="info" %}
You can create your menu elements. More info can be found [here](../other/custommenu.md).
{% endhint %}

## Functions

## RegisterCallback

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| event\_name | string | Event names |
| callback | function | Callback |

{% hint style="info" %}
You can view callbacks list [here](../other/callbacks.md).
{% endhint %}

```lua
cheat.RegisterCallback("draw", function()
    g_Render:Text("Hello world, it's me", Vector2.new(10.0, 15.0), Color.new(1.0, 1.0, 1.0), 16)
end)
```

## FireBullet

### Simulates bullet with wall penetrating

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| attacker | C\_BasePlayer | Attacker |
| start | Vector | Simluation start pos |
| end | Vector | Simluation end pos |

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| damage | float | Simulated damage |

```lua
local damage = cheat.FireBullet(player, Vector.new(0.0, 0.0, 0.0), Vector.new(1.0, 1.0, 1.0))
```

## AngleToForward

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| ang | QAngle | Input angle |

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| vec | Vector | Output vector |

```lua
local vec = cheat.AngleToForward(QAngle.new())
```

## VectorToAngle

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| vec | Vector | Input vector |

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| ang | QAngle | Output angle |

```lua
local ang = cheat.VectorToAngle(Vector.new())
```

## IsMenuVisible

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| value | bool | Is menu opened or not |

```lua
local is_visible = cheat.IsMenuVisible()
```

## GetMousePos

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| value | Vector2 | Mouse position on screen |

```lua
local mouse_pos = cheat.GetMousePos()
```

## IsKeyDown

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| key | int | Virtual key code |

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| value | bool | Is key down |

{% hint style="info" %}
You can find all virtual keys [here](https://docs.microsoft.com/en-us/windows/win32/inputdev/virtual-key-codes)
{% endhint %}

```lua
local mouse_pos = cheat.IsKeyDown(0x1)
```

## GetCheatUserName

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| name | string | Neverlose's account username |

```lua
local username = cheat.GetCheatUserName()
```

## GetEntitiesByClassID

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| id | int | Class id |

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| ent | C_BaseEntity* | |

```lua

```

## GetEntitiesByName

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| name | string | Entity name |

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| ent | C_BaseEntity* | |

```lua

```

## GetBinds

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| bind | ActiveBind | Binds |

```lua

```

## AddEvent

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| name | string | Event name |

```lua

```

## AddNotify

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| title | string | Event name |
| name | string | Event name |

```lua

```
