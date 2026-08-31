---
title: Signal
description: An event with callbacks and coroutine waiting.
---

Signals are exposed by Instances and services. A signal supports up to `512` active connections.

## Methods

### Connect(callback: `(...any) -> ()`): [`Connection`](/reference/datatypes/connection/)

Registers a callback. `connect` is a lowercase alias.

### Once(callback: `(...any) -> ()`): [`Connection`](/reference/datatypes/connection/)

Registers a callback that disconnects before its first call.

### Wait(): `...any`

Yields the current coroutine until the next event, then returns the values passed by that event.

### Fire(...: `any`): `()`

Runs connected callbacks and resumes waiting coroutines. `fire` is a lowercase alias.

```luau
local part = workspace:WaitForChild("Button")

local connection = part.Touched:Connect(function(otherPart)
    print(otherPart.Name)
end)

task.delay(10, function()
    connection:Disconnect()
end)
```

Callbacks run from a snapshot of the connection list, so disconnecting a callback does not disturb the rest of the current dispatch.
