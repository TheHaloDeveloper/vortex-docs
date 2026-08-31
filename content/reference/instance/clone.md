---
title: Clone
description: Creates a copy of an Instance and its descendants.
---

```luau
instance:Clone(): Instance
```

Returns a new copy of the Instance, including supported descendants. The clone has no parent until one is assigned. Engine-owned roots and other unsupported Instances cannot be cloned.

```luau
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Workspace = game:GetService("Workspace")
local effect = ReplicatedStorage:WaitForChild("Explosion"):Clone()

effect.Parent = Workspace
```
