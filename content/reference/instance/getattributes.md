---
title: GetAttributes
description: Returns every attribute on an Instance.
---

```luau
instance:GetAttributes(): {[string]: boolean | number | string}
```

Returns a table keyed by attribute name.

```luau
local objective = game:GetService("Workspace"):WaitForChild("Objective")

for name, value in pairs(objective:GetAttributes()) do
    print(name, value)
end
```
