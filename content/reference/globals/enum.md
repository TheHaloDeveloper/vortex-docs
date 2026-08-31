---
title: Enum
description: Global namespace for Vortex enum values.
---

`Enum` contains the enum types exposed to Luau. Reading an unknown enum or item raises an error.

## Enum types

| Type | Items |
| --- | --- |
| `Material` | `Smooth = 1`, `Plastic = 2`, `Wood = 3`, `Metal = 4`, `Grass = 5`, `Ice = 6`, `Paint = 7` |
| `NormalId` | `Right = 0`, `Top = 1`, `Back = 2`, `Left = 3`, `Bottom = 4`, `Front = 5` |
| `UserInputType` | `MouseButton1 = 0`, `MouseButton2 = 1`, `MouseButton3 = 2`, `MouseWheel = 3`, `MouseMovement = 4`, `Touch = 7`, `Keyboard = 8`, `Focus = 9`, `Gamepad1 = 12`, `None = 19` |
| `EasingStyle` | `Linear = 0`, `Sine = 1`, `Back = 2`, `Quad = 3`, `Quart = 4`, `Quint = 5`, `Bounce = 6`, `Elastic = 7`, `Exponential = 8`, `Circular = 9`, `Cubic = 10` |
| `EasingDirection` | `In = 0`, `Out = 1`, `InOut = 2` |
| `PlaybackState` | `Begin = 0`, `Delayed = 1`, `Playing = 2`, `Paused = 3`, `Completed = 4`, `Cancelled = 5` |

## KeyCode

| Group | Items |
| --- | --- |
| Control | `Unknown = 0`, `Backspace = 8`, `Tab = 9`, `Return = 13`, `Escape = 27`, `Space = 32`, `Delete = 127` |
| Punctuation | `Quote = 39`, `Comma = 44`, `Minus = 45`, `Period = 46`, `Slash = 47`, `Semicolon = 59`, `Equals = 61`, `LeftBracket = 91`, `BackSlash = 92`, `RightBracket = 93`, `Backquote = 96` |
| Digits | `Zero = 48`, `One = 49`, `Two = 50`, `Three = 51`, `Four = 52`, `Five = 53`, `Six = 54`, `Seven = 55`, `Eight = 56`, `Nine = 57` |
| Letters | `A = 97` through `Z = 122` |
| Arrows | `Up = 17`, `Down = 18`, `Right = 19`, `Left = 20` |
| Modifiers | `LeftShift = 304`, `RightShift = 303`, `LeftControl = 306`, `RightControl = 305`, `LeftAlt = 308`, `RightAlt = 307`, `LeftSuper = 311`, `RightSuper = 312` |
| Function keys | `F1 = 265` through `F12 = 276` |

Each type is an [`Enum`](/reference/datatypes/enum/), and each member is an [`EnumItem`](/reference/datatypes/enumitem/).

```luau
local style = Enum.EasingStyle.Quad
print(style.Name, style.Value)
```
