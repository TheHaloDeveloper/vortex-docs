---
title: Destroy
description: Removes an Instance and its descendants.
---

```luau
instance:Destroy()
```

Removes the Instance from its parent, destroys its descendants, and disconnects connections associated with it.

```luau
local effect = game:GetService("Workspace"):FindFirstChild("ExpiredEffect")

if effect then
    effect:Destroy()
end
```
