---
title: FindFirstChild
description: Finds a direct child by name.
---

```luau
instance:FindFirstChild(name: string): Instance?
```

Returns the first direct child with the given name. It returns `nil` when no matching child exists and does not search deeper descendants.

```luau
local Workspace = game:GetService("Workspace")
local door = Workspace:FindFirstChild("Door")

if door then
    door.Anchored = true
end
```
