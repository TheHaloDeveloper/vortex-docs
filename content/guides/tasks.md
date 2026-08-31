---
title: Tasks
description: Start, delay, and yield Luau coroutines.
---

The `task` library uses Vortex's cooperative scheduler. Waiting pauses the current coroutine, not every script.

## Functions

| Function | Description |
| --- | --- |
| `task.wait(seconds?)` | Yields for approximately the requested duration. The default is `0`. |
| `task.spawn(fn, ...)` | Starts the function immediately in a new coroutine. |
| `task.delay(seconds, fn, ...)` | Schedules the function to run after a delay. |
| `task.defer(fn, ...)` | Schedules the function with a delay of `0`. |

`task.spawn`, `task.delay`, and `task.defer` return their coroutine.

```luau
-- Script
local status = game:GetService("ReplicatedStorage"):WaitForChild("RoundStatus")

status.Value = "Round active"

task.delay(10, function()
    status.Value = "Round over"
end)
```

## Compatibility aliases

The global functions `wait`, `spawn`, and `delay` forward to `task.wait`, `task.spawn`, and `task.delay`.

See [Scripts and VMs](/guides/scripts-and-vms/) for the execution model.
