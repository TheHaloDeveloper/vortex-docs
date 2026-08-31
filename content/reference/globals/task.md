---
title: task
description: Schedules and suspends Luau coroutines.
---

## Functions

### task.wait(seconds: `number?`): `any`

Yields the current coroutine. `seconds` defaults to `0`.

### task.spawn(callbackOrThread: `function | thread`, ...: `any`): `thread`

Runs a function or resumes a coroutine immediately with the supplied arguments. An error is raised in the caller.

### task.delay(seconds: `number?`, callback: `function`, ...: `any`): `thread`

Schedules a new coroutine through the engine host. `seconds` defaults to `0`.

### task.defer(callback: `function`, ...: `any`): `thread`

Equivalent to `task.delay(0, callback, ...)`.

```luau
local status = workspace:WaitForChild("RoundStatus")

task.delay(10, function(value)
    status.Value = value
end, "Finished")

task.wait(0.25)
```
