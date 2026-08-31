---
title: Players
description: The service containing connected Player Instances.
---

## Summary

`Players` is an engine-owned service returned by `game:GetService("Players")`. Its children are [Player](/reference/classes/player/) Instances.

## Properties

| Member | Description |
| --- | --- |
| `LocalPlayer: Player?` | The Player for the current client. It is `nil` outside a client context. |

Players inherits the common [Instance](/reference/classes/instance/) members, including `GetChildren()`.

## Example

```luau
local Players = game:GetService("Players")

for _, player in ipairs(Players:GetChildren()) do
    if player:IsA("Player") then
        print(player.Name)
    end
end
```
