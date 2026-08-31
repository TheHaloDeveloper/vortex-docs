---
title: Part
description: A 3D scene object with transform, appearance, physics, and touch members.
---

## Summary

`Part` is the main scriptable world object. Create one with `Instance.new("Part")`, set its properties, then parent it to [Workspace](/reference/classes/workspace/) to place it in the scene.

## Transform properties

| Member | Description |
| --- | --- |
| `Position: Vector3` | World position. |
| `Rotation: Vector3` | Euler rotation. `Orientation` is an alias. |
| `CFrame: CFrame` | Full position and rotation transform. |
| `Size: Vector3` | Width, height, and depth. |

## Appearance and physics

| Member | Description |
| --- | --- |
| `Color: Color3` | Surface color. |
| `Transparency: number` | Transparency value. The bridge rejects non-finite numbers. |
| `Anchored: boolean` | Prevents physics from moving the Part when true. |
| `CanCollide: boolean` | Controls physical collision. |
| `CastShadow: boolean` | Controls whether the Part casts a shadow. |

## Events

| Member | Description |
| --- | --- |
| `Touched: Signal` | Fires when a collision contact begins. |
| `TouchEnded: Signal` | Fires when a collision contact ends. |

Part also inherits the common [Instance](/reference/classes/instance/) members.

## Example

```luau
local Workspace = game:GetService("Workspace")

local pad = Instance.new("Part")
pad.Name = "DamagePad"
pad.Size = Vector3.new(8, 1, 8)
pad.Position = Vector3.new(0, 2, 0)
pad.Color = Color3.fromRGB(235, 80, 80)
pad.Anchored = true
pad.Parent = Workspace

pad.Touched:Connect(function(otherPart)
    print(otherPart.Name, "touched the pad")
end)
```
