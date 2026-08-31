---
title: Player
description: Represents one connected player.
---

## Summary

`Player` Instances are engine-owned children of the [Players](/reference/classes/players/) service. They are not supported `Instance.new` targets.

## Properties

| Member | Description |
| --- | --- |
| `Character: Model?` | The player's current character, or `nil` when no character is present. |

Player also inherits `Name`, `Parent`, and the other common [Instance](/reference/classes/instance/) members.

## Example

```luau
local Players = game:GetService("Players")
local player = Players.LocalPlayer

if player then
    print("Hello, " .. player.Name)

    if player.Character then
        print("Character:", player.Character.Name)
    end
end
```
