---
title: PointLight
description: A light that emits in every direction from its parent Part.
---

## Summary

`PointLight` is a supported `Instance.new` target. Parent it to a [Part](/reference/classes/part/) to place the light in the scene.

## Properties

| Member | Description |
| --- | --- |
| `Color: Color3` | Color of the emitted light. |
| `Brightness: number` | Intensity of the light. |
| `Range: number` | Maximum distance reached by the light. |

PointLight also inherits the common [Instance](/reference/classes/instance/) members.

## Example

```luau
local Workspace = game:GetService("Workspace")
local lamp = Workspace:WaitForChild("Lamp")

local light = Instance.new("PointLight")
light.Color = Color3.fromRGB(255, 220, 170)
light.Brightness = 2
light.Range = 18
light.Parent = lamp
```
