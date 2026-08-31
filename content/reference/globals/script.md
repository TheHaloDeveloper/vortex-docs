---
title: script
description: The Script, LocalScript, or ModuleScript currently running.
---

`script` refers to the Instance that owns the current source. It supports the same properties and methods as other Instances.

```luau
print(script.Name, script.ClassName)

local settings = script:FindFirstChild("Settings")
if settings then
    print(settings.Name)
end
```
