---
title: IsA
description: Checks whether an Instance belongs to a class.
---

```luau
instance:IsA(className: string): boolean
```

Returns whether the Instance matches the given class.

```luau
for _, item in ipairs(game:GetService("Workspace"):GetDescendants()) do
    if item:IsA("Part") then
        item.CastShadow = false
    end
end
```
