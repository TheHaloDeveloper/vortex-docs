---
title: IntValue
description: An Instance that stores a numeric value.
---

## Summary

`IntValue` stores a number in its `Value` property. It can be created with `Instance.new("IntValue")` and inherits the common [Instance](/reference/classes/instance/) members.

## Properties

| Member | Description |
| --- | --- |
| `Value: number` | The stored value. |

## Example

```luau
local ReplicatedStorage = game:GetService("ReplicatedStorage")

local score = Instance.new("IntValue")
score.Name = "Score"
score.Value = 0
score.Parent = ReplicatedStorage

score:GetPropertyChangedSignal("Value"):Connect(function()
    print("Score:", score.Value)
end)

score.Value = 10
```
