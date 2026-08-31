---
title: Your First Script
description: Create and place a Part from a server Script.
---

Create a `Script` in `ServerScriptService`, then replace its source with:

```luau
local Workspace = game:GetService("Workspace")

local part = Instance.new("Part")
part.Name = "MyPart"
part.Size = Vector3.new(2, 2, 2)
part.Position = Vector3.new(0, 10, 0)
part.Color = Color3.fromRGB(192, 32, 12)
part.Anchored = false
part.Parent = Workspace
```

Start a playtest. The Script creates an unanchored red Part ten studs above the origin.

`Parent` is assigned last so the Part enters the scene after its other properties are ready.
