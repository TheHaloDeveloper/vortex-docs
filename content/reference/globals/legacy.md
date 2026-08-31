---
title: Legacy globals
description: Older scheduling functions kept for compatibility.
---

These globals forward to the [`task`](/reference/globals/task/) library.

| Global | Equivalent |
| --- | --- |
| `wait(seconds: number?): any` | `task.wait(seconds)` |
| `spawn(callback: function): thread` | `task.spawn(callback)` |
| `delay(seconds: number?, callback: function): thread` | `task.delay(seconds, callback)` |

```luau
delay(1, function()
    print("One second later")
end)
```

New code should use `task.wait`, `task.spawn`, and `task.delay` directly because the task versions accept callback arguments.
