---
title: Workspace
description: The root of the scriptable scene hierarchy.
---

## Summary

`Workspace` contains the Parts, Models, and other scene Instances used by the running game. It is an engine-owned service returned by `game:GetService("Workspace")`, not a supported `Instance.new` target.

Workspace does not add class-specific properties or methods in the current Luau bridge. Its useful API comes from [Instance](/reference/classes/instance/).

## Members

| Member | Description |
| --- | --- |
| `Name: string` | The service name. |
| `ClassName: string` | Read-only class name. |
| `GetChildren(): {Instance}` | Returns the top-level scene Instances. |
| `GetDescendants(): {Instance}` | Returns every Instance below Workspace. |
| `FindFirstChild(name: string): Instance?` | Finds a top-level child by name. |
| `WaitForChild(name: string, timeout?: number): Instance?` | Waits for a top-level child, with an optional timeout. |
| `FindFirstChildOfClass(className: string): Instance?` | Finds a top-level child by class. |
| `GetPropertyChangedSignal(property: string): Signal` | Returns a signal for a Workspace property. |
| `SetAttribute(name: string, value)` | Sets or removes a Workspace attribute. |
| `GetAttribute(name: string)` | Reads a Workspace attribute. |
| `GetAttributes()` | Returns all Workspace attributes. |
| `GetAttributeChangedSignal(name: string): Signal` | Returns a signal for one Workspace attribute. |

No raycast method is exposed by the current verified bridge.

## Example

```luau
local Workspace = game:GetService("Workspace")
local platform = Workspace:WaitForChild("Platform", 5)

if platform and platform:IsA("Part") then
    platform.Anchored = true
    platform.Position = Vector3.new(0, 4, 0)
    platform.Color = Color3.fromRGB(92, 170, 255)
end

for _, item in ipairs(Workspace:GetDescendants()) do
    if item:IsA("Part") then
        print(item.Name, item.Position)
    end
end
```
