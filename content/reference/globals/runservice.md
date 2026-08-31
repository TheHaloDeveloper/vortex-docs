---
title: RunService
description: Exposes the engine update signal.
---

`RunService` is available as a global and through `game:GetService("RunService")`.

## Events

### Heartbeat: [`Signal`](/reference/datatypes/signal/)

Fires once per engine update. The first value is the elapsed time since the previous update, in seconds. Active tweens are advanced from this signal.

```luau
local RunService = game:GetService("RunService")
local elapsed = 0

RunService.Heartbeat:Connect(function(deltaTime)
    elapsed += deltaTime
end)
```
