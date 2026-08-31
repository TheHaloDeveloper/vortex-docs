---
title: GetAttributeChangedSignal
description: Returns a Signal for changes to one attribute.
---

```luau
instance:GetAttributeChangedSignal(name: string): Signal
```

The returned Signal fires when the named attribute is created, changed, or removed.

```luau
local objective = game:GetService("Workspace"):WaitForChild("Objective")

objective:GetAttributeChangedSignal("Captured"):Connect(function()
    print(objective:GetAttribute("Captured"))
end)
```
