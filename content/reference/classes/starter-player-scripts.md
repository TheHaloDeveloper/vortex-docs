---
title: StarterPlayerScripts
description: The engine-owned template container for client scripts.
---

## Summary

`StarterPlayerScripts` is returned by `game:GetService("StarterPlayerScripts")`. It is a service root, not a supported `Instance.new` target.

It has no verified class-specific members and inherits the common [Instance](/reference/classes/instance/) hierarchy methods.

## Example

```luau
local StarterPlayerScripts = game:GetService("StarterPlayerScripts")

for _, item in ipairs(StarterPlayerScripts:GetChildren()) do
    print(item.Name, item.ClassName)
end
```
