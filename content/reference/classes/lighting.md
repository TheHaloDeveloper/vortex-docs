---
title: Lighting
description: Editor settings for the scene's ambient and directional light.
---

## Summary

`Lighting` is an editor-owned scene object. The current build does not return it from `game:GetService`, so the settings on this page are not scriptable Luau properties.

## Editor properties

| Property | Description |
| --- | --- |
| Ambient Color | Color applied to surfaces regardless of their direction. |
| Brightness | Intensity of the ambient light. |
| Sun Color | Color of direct sunlight. |
| Sun Brightness | Intensity of direct sunlight. |
| Sun Shadows | Enables or disables sun shadows. |
| Rotation | Changes the direction from which sunlight reaches the scene. |

The Position and Size fields shown by the editor do not affect lighting.
