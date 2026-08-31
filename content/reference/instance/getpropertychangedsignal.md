---
title: GetPropertyChangedSignal
description: Returns a Signal for changes to one property.
---

```luau
instance:GetPropertyChangedSignal(propertyName: string): Signal
```

The returned Signal fires after the named property changes.

```luau
local score = game:GetService("ReplicatedStorage"):WaitForChild("Score")

score:GetPropertyChangedSignal("Value"):Connect(function()
    print("Score:", score.Value)
end)
```
