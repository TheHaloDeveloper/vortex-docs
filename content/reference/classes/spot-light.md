---
title: SpotLight
description: A conical light emitted from one face of its parent Part.
---

## Summary

`SpotLight` is a supported `Instance.new` target. Parent it to a [Part](/reference/classes/part/) to place and orient the light.

## Properties

| Member | Description |
| --- | --- |
| `Color: Color3` | Color of the emitted light. |
| `Brightness: number` | Intensity of the light. |
| `Range: number` | Maximum distance reached by the light. |
| `Angle: number` | Width of the emission cone. |
| `Face: Enum.NormalId` | Face of the parent Part from which the light emits. |

SpotLight also inherits the common [Instance](/reference/classes/instance/) members.

## Example

```luau
local Workspace = game:GetService("Workspace")
local fixture = Workspace:WaitForChild("Fixture")

local light = Instance.new("SpotLight")
light.Color = Color3.fromRGB(180, 215, 255)
light.Brightness = 3
light.Range = 24
light.Angle = 45
light.Face = Enum.NormalId.Front
light.Parent = fixture
```
