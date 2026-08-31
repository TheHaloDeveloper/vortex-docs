---
title: Instances
description: Create objects and work with the Vortex object hierarchy.
---

Instances are the objects in a Vortex game. Services, scene objects, scripts, values, and remotes all use the same base API.

## Creating an Instance

`Instance.new(className)` creates a supported class. Set its properties, then assign `Parent` to place it in the hierarchy.

```luau
local Workspace = game:GetService("Workspace")

local platform = Instance.new("Part")
platform.Name = "Platform"
platform.Size = Vector3.new(8, 1, 8)
platform.Anchored = true
platform.Parent = Workspace
```

Engine-owned roots such as `Workspace` are services and cannot be created with `Instance.new`.

## Finding objects

| Method | Description |
| --- | --- |
| `GetChildren()` | Returns the Instance's direct children. |
| `GetDescendants()` | Returns every descendant below the Instance. |
| `FindFirstChild(name)` | Returns a direct child with that name, or `nil`. |
| `WaitForChild(name, timeout?)` | Yields until a direct child appears or the timeout expires. |
| `FindFirstChildOfClass(className)` | Returns the first direct child of that class, or `nil`. |
| `IsA(className)` | Checks the Instance's class. |

## Lifetime

`Clone()` copies a supported Instance and its descendants. `Destroy()` removes an Instance and its descendants and disconnects their connections.
