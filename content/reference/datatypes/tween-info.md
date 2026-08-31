---
title: TweenInfo
description: Timing and easing settings used to create a Tween.
---

## Constructor

### TweenInfo.new(time: `number?`, easingStyle: `Enum.EasingStyle?`, easingDirection: `Enum.EasingDirection?`, repeatCount: `number?`, reverses: `boolean?`, delayTime: `number?`): `TweenInfo`

```luau
local info = TweenInfo.new(
    0.5,
    Enum.EasingStyle.Quad,
    Enum.EasingDirection.Out,
    1,
    true,
    0.1
)
```

## Properties

| Property | Default | Description |
| --- | --- | --- |
| `Time` | `1` | Duration of one pass, in seconds. |
| `EasingStyle` | `Enum.EasingStyle.Quad` | Curve used for interpolation. |
| `EasingDirection` | `Enum.EasingDirection.Out` | Which side of the curve receives easing. |
| `RepeatCount` | `0` | Additional play cycles. A negative value repeats indefinitely. |
| `Reverses` | `false` | Plays back toward the starting value after each forward pass. |
| `DelayTime` | `0` | Delay before interpolation begins, in seconds. |
