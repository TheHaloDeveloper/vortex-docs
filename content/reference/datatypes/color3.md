---
title: Color3
description: A color stored as red, green, and blue components.
---

`Color3` stores each color channel as a number from `0` to `1`.

## Constructors

### Color3.new(r: `number?`, g: `number?`, b: `number?`): `Color3`

Creates a color from normalized channel values. Missing values default to `0`.

### Color3.fromRGB(r: `number?`, g: `number?`, b: `number?`): `Color3`

Creates a color from channel values in the `0` to `255` range.

```luau
local blue = Color3.fromRGB(60, 130, 255)
local darkBlue = Color3.new(0.1, 0.2, 0.5)
```

## Properties

| Property | Type | Description |
| --- | --- | --- |
| `R` | `number` | Red channel. |
| `G` | `number` | Green channel. |
| `B` | `number` | Blue channel. |

## Methods

### Lerp(goal: `Color3`, alpha: `number`): `Color3`

Interpolates each channel toward `goal`.

```luau
local purple = Color3.fromRGB(255, 0, 0):Lerp(Color3.fromRGB(0, 0, 255), 0.5)
```

`Color3` values can be compared with `==` and converted to a readable string with `tostring`.
