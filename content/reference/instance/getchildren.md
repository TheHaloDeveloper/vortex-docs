---
title: GetChildren
description: Returns the direct children of an Instance.
---

```luau
instance:GetChildren(): {Instance}
```

Returns a new array containing each direct child. Nested descendants are not included.

```luau
local folder = game:GetService("Workspace"):WaitForChild("Props")

for _, child in ipairs(folder:GetChildren()) do
    print(child.Name)
end
```
