---
title: Events
description: Connect and consume runtime signals in Vortex.
---

## Signals

Events are represented by [`Signal`](/content/reference/datatypes/signal.md)
values. Connect a callback with `:Connect`, keep the returned
[`Connection`](/content/reference/datatypes/connection.md), and disconnect it
when the listener is no longer needed.

```lua
local connection = game:GetService("RunService").Heartbeat:Connect(function(deltaTime)
    print(deltaTime)
end)

connection:Disconnect()
```

`Once` and `Wait` are also available. `ConnectParallel` is not exposed.

## Delivery limits

Manual `Signal:Fire(...)` delivery works for standalone and supported signals.
Some instance change signals are only partially implemented: they can be
connected but do not fire when the corresponding property or attribute is
written. `Part.Changed`, user input, Humanoid health signals, and remote-event
signals each need to be treated according to their documented runtime behavior.

Do not use a connectable signal as proof that a producer exists. Confirm that
the specific event delivers in the context where your code runs.
