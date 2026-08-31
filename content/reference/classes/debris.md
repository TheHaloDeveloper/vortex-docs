---
title: Debris
description: Schedules an Instance to be destroyed later.
---

## Summary

`Debris` is a service returned by `game:GetService("Debris")`. Use it for temporary Instances when a script should not yield while waiting to remove them.

## Methods

| Member | Description |
| --- | --- |
| `Debris:AddItem(item: Instance, lifetime?: number)` | Calls `Destroy()` after `lifetime` seconds. The default is 10 seconds. Passing `nil` does nothing. |
| `Debris:SetMaxItems()` | Compatibility method with no effect in the current build. |

## Example

```luau
local Debris = game:GetService("Debris")
local Workspace = game:GetService("Workspace")

local marker = Instance.new("Part")
marker.Name = "TemporaryMarker"
marker.Anchored = true
marker.Parent = Workspace

Debris:AddItem(marker, 3)
```
