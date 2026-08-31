---
title: StringValue
description: An Instance that stores text.
---

## Summary

`StringValue` stores text in its `Value` property. It can be created with `Instance.new("StringValue")` and inherits the common [Instance](/reference/classes/instance/) members.

## Properties

| Member | Description |
| --- | --- |
| `Value: string` | The stored text. |

## Example

```luau
local ReplicatedStorage = game:GetService("ReplicatedStorage")

local status = Instance.new("StringValue")
status.Name = "RoundStatus"
status.Value = "Waiting"
status.Parent = ReplicatedStorage

status:GetPropertyChangedSignal("Value"):Connect(function()
    print(status.Value)
end)

status.Value = "Round started"
```
