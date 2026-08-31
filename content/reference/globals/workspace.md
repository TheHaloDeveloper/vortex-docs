---
title: workspace
description: Global reference to the Workspace service.
---

`workspace` is the scene root. It is the same object returned by `game:GetService("Workspace")`.

```luau
local platform = workspace:WaitForChild("Platform")
platform.Position = Vector3.new(0, 6, 0)
```

Instances may not exist when a script starts. Use `WaitForChild`, `FindFirstChild`, or another tree method when load order is uncertain.

See [`Workspace`](/reference/classes/workspace/) for its class members and inherited Instance API.
