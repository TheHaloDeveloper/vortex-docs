---
title: BoolValue
description: BoolValue is not exposed by the current Luau Instance bridge.
---

## Summary

`BoolValue` has an existing reference page, but the current Luau bridge does not accept `Instance.new("BoolValue")` and no `Value` member is exposed.

Use an attribute when a script needs to store a boolean on an Instance.

```luau
local door = game:GetService("Workspace"):WaitForChild("Door")

door:SetAttribute("Locked", true)
print(door:GetAttribute("Locked"))
```
