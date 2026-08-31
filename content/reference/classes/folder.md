---
title: Folder
description: A general-purpose container for Instances.
---

## Summary

`Folder` groups Instances without adding transform or rendering behavior. It inherits the members of [Instance](/reference/classes/instance/).

## Members

`Folder` has no class-specific members in the current build.

## Example

```luau
local ReplicatedStorage = game:GetService("ReplicatedStorage")

local effects = Instance.new("Folder")
effects.Name = "Effects"
effects.Parent = ReplicatedStorage
```
