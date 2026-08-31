---
title: Enum
description: A named collection of EnumItem values.
---

An enum type such as `Enum.Material` groups related [`EnumItem`](/reference/datatypes/enumitem/) values.

## Properties

| Property | Type | Description |
| --- | --- | --- |
| `Name` | `string` | Name of the enum type. |

## Methods

### GetEnumItems(): `{ EnumItem }`

Returns the items in declaration order. The returned array is a copy.

### FromName(name: `string`): `EnumItem?`

Returns the item with the given name, or `nil`.

### FromValue(value: `number`): `EnumItem?`

Returns the item with the given numeric value, or `nil`.

```luau
local material = Enum.Material:FromName("Metal")

for _, item in Enum.Material:GetEnumItems() do
    print(item.Name, item.Value)
end
```
