---
title: SetAttribute
description: Creates, changes, or removes an attribute.
---

```luau
instance:SetAttribute(name: string, value: boolean | number | string | nil)
```

Passing `nil` removes the named attribute.

```luau
local round = game:GetService("ReplicatedStorage")

round:SetAttribute("Active", true)
round:SetAttribute("TimeLeft", 60)
```
