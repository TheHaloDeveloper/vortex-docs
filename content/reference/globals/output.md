---
title: Output globals
description: Writes messages and errors to the Studio Luau console.
---

| Global | Behavior |
| --- | --- |
| `print(...: any): ()` | Writes a normal output entry. |
| `warn(...: any): ()` | Writes a warning entry. |
| `error(message: any): never` | Stops the current call and reports the error. |

Multiple values passed to `print` or `warn` are separated by tabs.

```luau
print("Loaded", 3, "modules")
warn("Using fallback configuration")
```
