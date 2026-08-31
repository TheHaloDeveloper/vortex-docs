---
title: Model
description: A hierarchy container used to group scene Instances.
---

## Summary

`Model` groups related Instances. It is a supported `Instance.new` target and inherits the hierarchy, attribute, and lifecycle members of [Instance](/reference/classes/instance/).

## Members

No class-specific Luau members are verified in the current build. Transform properties belong to the Parts inside the Model.

## Example

```luau
local Workspace = game:GetService("Workspace")

local model = Instance.new("Model")
model.Name = "Checkpoint"
model.Parent = Workspace

local marker = Instance.new("Part")
marker.Name = "Marker"
marker.Anchored = true
marker.Position = Vector3.new(0, 4, 0)
marker.Parent = model
```
