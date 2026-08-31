---
title: GetDescendants
description: Returns every descendant below an Instance.
---

```luau
instance:GetDescendants(): {Instance}
```

Returns a new array containing children, grandchildren, and all deeper descendants.

```luau
local map = game:GetService("Workspace"):WaitForChild("Map")

for _, item in ipairs(map:GetDescendants()) do
    if item:IsA("Part") then
        item.Anchored = true
    end
end
```
