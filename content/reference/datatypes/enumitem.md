---
title: EnumItem
description: One named value in an Enum.
---

Enum members such as `Enum.EasingStyle.Quad` are `EnumItem` values.

## Properties

| Property | Type | Description |
| --- | --- | --- |
| `Name` | `string` | Item name. |
| `Value` | `number` | Numeric value. |
| `EnumType` | [`Enum`](/reference/datatypes/enum/) | Enum that owns the item. |

```luau
local item = Enum.EasingStyle.Quad
print(item.Name)       -- Quad
print(item.Value)      -- 3
print(item.EnumType)   -- Enum.EasingStyle
```

Two items compare equal when they have the same name and belong to the same enum. `tostring(item)` returns its full path, such as `Enum.EasingStyle.Quad`.
