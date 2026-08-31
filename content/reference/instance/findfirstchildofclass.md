---
title: FindFirstChildOfClass
description: Finds a direct child by class.
---

```luau
instance:FindFirstChildOfClass(className: string): Instance?
```

Returns the first direct child whose class matches `className`, or `nil` when no match exists.

```luau
local character = game:GetService("Workspace"):WaitForChild("Character")
local humanoid = character:FindFirstChildOfClass("Humanoid")

if humanoid then
    print(humanoid.Health)
end
```
