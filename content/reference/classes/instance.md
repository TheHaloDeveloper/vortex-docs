---
title: Instance
description: The base object for services, scene objects, scripts, and networking endpoints.
---

## Summary

Every object exposed through the Vortex Instance bridge inherits this API. Instances form a parent-child hierarchy and can carry named attributes.

## Properties

| Member | Description |
| --- | --- |
| `Name: string` | The Instance name. |
| `ClassName: string` | Read-only class name. |
| `Parent: Instance?` | Parent in the hierarchy. Assign another Instance or `nil`. |

## Hierarchy methods

| Member | Description |
| --- | --- |
| `GetChildren(): {Instance}` | Returns the direct children. |
| `GetDescendants(): {Instance}` | Returns all descendants. |
| `FindFirstChild(name: string): Instance?` | Finds a direct child by name. |
| `WaitForChild(name: string, timeout?: number): Instance?` | Waits for a direct child, polling every 0.05 seconds. Returns `nil` after the optional timeout. |
| `FindFirstChildOfClass(className: string): Instance?` | Finds a direct child with the given class. |
| `IsA(className: string): boolean` | Tests the Instance's class identity or ancestry. |

## Properties and attributes

| Member | Description |
| --- | --- |
| `GetPropertyChangedSignal(property: string): Signal` | Returns a signal for changes to a named property. |
| `SetAttribute(name: string, value: boolean \| number \| string \| nil)` | Sets an attribute. Passing `nil` removes it. |
| `GetAttribute(name: string): boolean \| number \| string \| nil` | Reads one attribute. |
| `GetAttributes(): {[string]: boolean \| number \| string}` | Returns the current attributes. |
| `GetAttributeChangedSignal(name: string): Signal` | Returns a signal for changes to one attribute. |

Attribute values are limited to `nil`, `boolean`, `number`, and `string`.

## Lifecycle

| Member | Description |
| --- | --- |
| `Instance.new(className: string): Instance` | Creates a supported class. |
| `Clone(): Instance` | Copies a supported Instance. Engine-owned roots cannot be cloned. |
| `Destroy()` | Destroys the Instance and removes it from the hierarchy. |

Supported constructor targets are `Part`, `Model`, `Folder`, `PointLight`, `SpotLight`, `LocalScript`, `Script`, `ModuleScript`, `RemoteEvent`, `BindableEvent`, `RemoteFunction`, `IntValue`, and `StringValue`.

## Example

```luau
local Workspace = game:GetService("Workspace")
local objective = Workspace:WaitForChild("Objective")

objective:GetAttributeChangedSignal("Captured"):Connect(function()
    local captured = objective:GetAttribute("Captured")
    objective.Color = captured
        and Color3.fromRGB(90, 190, 120)
        or Color3.fromRGB(235, 80, 80)
end)

for _, item in ipairs(Workspace:GetDescendants()) do
    if item:IsA("Part") then
        print(item.Name)
    end
end
```
