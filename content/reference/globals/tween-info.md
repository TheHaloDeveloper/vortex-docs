---
title: TweenInfo
description: Comprehensive API reference and guide for the Roblox TweenInfo datatype used with TweenService.
---

`TweenInfo` is a immutable Luau data structure that defines the playback parameters for a `Tween` created via [`TweenService`](https://create.roblox.com/docs/reference/engine/classes/TweenService). 

It controls **how long** an animation lasts, **how** property values transition over time (easing curves), **how many times** the animation repeats, whether it **reverses**, and any **delay** before playing.
By setting the repeatCount to -1, it'll repeat forever

---

## Constructor

### `TweenInfo.new()`

Creates a new `TweenInfo` object. All parameters are optional; if omitted, they will fall back to their default values.

```luau
TweenInfo.new(
    time: number?,
    easingStyle: Enum.EasingStyle?,
    easingDirection: Enum.EasingDirection?,
    repeatCount: number?,
    reverses: boolean?,
    delayTime: number?
): TweenInfo
