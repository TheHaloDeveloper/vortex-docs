---
title: Sandbox Limits
description: Limits enforced by the Luau runtime and Studio executor.
---

These limits apply to Vortex Studio v0.3.4. They are safety ceilings and may change in later builds.

## Gameplay runtime

| Resource | Limit |
| --- | --- |
| Connections | 512 handlers on one `Signal` |
| Tweens | 256 active tweens |
| Remote events | 512 fires per script, per frame |
| Property changes | 50,000 changes per script, per frame |

The host also rejects scripts that build up too many pending task threads. Remote payloads have a nesting limit; supported payload types are listed in [Values](/guides/values/).

If several events can happen in one frame, collect their data and send one payload:

```luau
-- LocalScript
local RunService = game:GetService("RunService")
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local sensor = game:GetService("Workspace"):WaitForChild("Sensor")
local remote = ReplicatedStorage:WaitForChild("SensorTouches")
local pending = {}

sensor.Touched:Connect(function(part)
    table.insert(pending, part.Name)
end)

RunService.Heartbeat:Connect(function()
    if #pending == 0 then
        return
    end

    remote:FireServer(pending)
    pending = {}
end)
```

## Studio executor

| Resource | Limit |
| --- | --- |
| Source | 128 KiB per editor snippet |
| Memory | 32 MiB |
| Run time | 2 seconds |
| Console history | 256 entries |
| Console line | 4096 bytes |

These Studio limits apply to executor snippets, not ordinary gameplay scripts.
