---
title: ReplicatedStorage
description: A shared Instance container available to server and client scripts.
---

## Summary

`ReplicatedStorage` is an engine-owned service returned by `game:GetService("ReplicatedStorage")`. Use it for Instances that both sides need to find, such as remote endpoints and shared values.

It has no verified class-specific members. Use the inherited [Instance](/reference/classes/instance/) hierarchy methods to access its contents.

## Example

```luau
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local roundEvent = ReplicatedStorage:WaitForChild("RoundEvent")

print(roundEvent.ClassName)
```
