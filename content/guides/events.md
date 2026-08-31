---
title: Events
description: Respond to changes and gameplay events with Signals.
---

Events are [Signal](/reference/datatypes/signal/) values exposed by Instances and services.

## Listening to an event

| Method | Description |
| --- | --- |
| `signal:Connect(callback)` | Runs the callback whenever the signal fires and returns a Connection. |
| `signal:Once(callback)` | Runs the callback once, then disconnects it. |
| `signal:Wait()` | Yields until the signal next fires and returns its arguments. |
| `connection:Disconnect()` | Stops a connected callback from running again. |

Keep the returned [Connection](/reference/datatypes/connection/) when a listener needs to be removed later.

## Common events

| Event | Description |
| --- | --- |
| `Part.Touched` | Fires when a collision contact begins. |
| `Part.TouchEnded` | Fires when a collision contact ends. |
| `Humanoid.HealthChanged` | Fires when health changes. |
| `Humanoid.Died` | Fires when the Humanoid reaches the death state. |
| `RunService.Heartbeat` | Fires once per engine update. |

## Example

```luau
local Workspace = game:GetService("Workspace")
local pad = Workspace:WaitForChild("DamagePad")
local idleColor = Color3.fromRGB(235, 80, 80)

pad.Touched:Connect(function()
    pad.Color = Color3.fromRGB(255, 210, 90)
end)

pad.TouchEnded:Connect(function()
    pad.Color = idleColor
end)
```
