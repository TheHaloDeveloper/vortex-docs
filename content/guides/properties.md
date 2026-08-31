---
title: Properties
description: Read, change, and observe properties and attributes on Instances.
---

Properties store an [Instance](/reference/classes/instance/)'s built-in state. Read or assign them with dot syntax, such as `part.Transparency = 0.5`.

`ClassName` identifies the Instance's class and is read-only. `Parent` accepts another Instance or `nil`.

## Property changes

`GetPropertyChangedSignal` returns a [Signal](/reference/datatypes/signal/) for one property.

```luau
instance:GetPropertyChangedSignal(propertyName: string): Signal
```

The signal fires after that property changes.

## Attributes

Attributes are custom named values rather than built-in properties. They support `boolean`, `number`, and `string` values; assigning `nil` removes an attribute. See the [Attributes guide](/guides/attributes/) for its methods.

## Example

This changes an objective's transparency when its `Captured` attribute changes.

```luau
local Workspace = game:GetService("Workspace")
local objective = Workspace:WaitForChild("Objective")

objective:GetPropertyChangedSignal("Transparency"):Connect(function()
    print("Transparency:", objective.Transparency)
end)

objective:GetAttributeChangedSignal("Captured"):Connect(function()
    local captured = objective:GetAttribute("Captured")
    objective.Transparency = captured and 0 or 0.5
end)

objective:SetAttribute("Captured", true)
```
