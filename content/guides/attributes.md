---
title: Attributes
description: Store custom values on an Instance and react when they change.
---

Attributes are named values attached to an Instance. Unlike properties, their names are defined by your game.

This build accepts `boolean`, `number`, and `string` values. Passing `nil` removes the attribute.

## Methods

| Method | Description |
| --- | --- |
| `instance:SetAttribute(name, value)` | Creates, changes, or removes an attribute. |
| `instance:GetAttribute(name)` | Returns the value, or `nil` when the attribute does not exist. |
| `instance:GetAttributes()` | Returns a table containing every attribute on the Instance. |
| `instance:GetAttributeChangedSignal(name)` | Returns a Signal that fires when the named attribute changes. |

## Example

```luau
local objective = game:GetService("Workspace"):WaitForChild("Objective")

objective:GetAttributeChangedSignal("Captured"):Connect(function()
    print("Captured:", objective:GetAttribute("Captured"))
end)

objective:SetAttribute("Captured", true)
```
