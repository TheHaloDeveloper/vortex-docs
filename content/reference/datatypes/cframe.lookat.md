---
title: CFrame.lookAt
description: Creates a CFrame positioned at one point and facing another.
---

## CFrame.lookAt(position: Vector3, target: Vector3): CFrame

Returns a `CFrame` at `position` oriented toward `target`.

```luau
local position = Vector3.new(0, 5, 0)
local target = Vector3.new(0, 5, -10)

local transform = CFrame.lookAt(position, target)
```

The constructor is also documented on [CFrame](/reference/datatypes/cframe/).
