---
title: ServerScriptService
description: The engine-owned container for server scripts.
---

## Summary

`ServerScriptService` is returned by `game:GetService("ServerScriptService")`. It is a service root, not a supported `Instance.new` target.

It has no verified class-specific members and inherits the common [Instance](/reference/classes/instance/) hierarchy methods.

## Example

```luau
local ServerScriptService = game:GetService("ServerScriptService")

for _, item in ipairs(ServerScriptService:GetChildren()) do
    print(item.Name, item.ClassName)
end
```
