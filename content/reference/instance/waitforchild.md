---
title: WaitForChild
description: Waits for a direct child to appear.
---

```luau
instance:WaitForChild(name: string, timeout: number?): Instance?
```

Yields until a direct child with the given name exists. When `timeout` is supplied, the method returns `nil` if that many seconds pass first.

```luau
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local status = ReplicatedStorage:WaitForChild("RoundStatus", 5)

if status then
    print(status.Value)
end
```
