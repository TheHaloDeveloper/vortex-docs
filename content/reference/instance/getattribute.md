---
title: GetAttribute
description: Reads one attribute from an Instance.
---

```luau
instance:GetAttribute(name: string): boolean | number | string | nil
```

Returns the stored value, or `nil` when the attribute does not exist.

```luau
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local active = ReplicatedStorage:GetAttribute("Active")

print(active)
```
