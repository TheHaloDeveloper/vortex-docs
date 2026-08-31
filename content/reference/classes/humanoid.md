---
title: Humanoid
description: Holds a character's health and death signals.
---

## Summary

`Humanoid` is an engine-owned character Instance. It is not a supported target for `Instance.new`.

## Members

| Member | Description |
| --- | --- |
| `Health: number` | Current character health. Client scripts may read it, but health writes are server-authoritative. |
| `HealthChanged: Signal` | Fires when `Health` changes. |
| `Died: Signal` | Fires when the Humanoid reaches its death state. |

Humanoid also inherits the common [Instance](/reference/classes/instance/) members.

## Example

```luau
local Players = game:GetService("Players")
local player = Players.LocalPlayer
local character = player and player.Character
local humanoid = character and character:FindFirstChildOfClass("Humanoid")

if humanoid then
    humanoid.HealthChanged:Connect(function(health)
        print("Health:", health)
    end)

    humanoid.Died:Connect(function()
        print("Character died")
    end)
end
```
