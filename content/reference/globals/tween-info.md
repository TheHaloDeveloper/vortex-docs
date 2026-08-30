---
title: TweenInfo
description: information to give to the tween service to create a new tween
---

## METHODS
.new(
  time:int,
  easingStyle:?Enum.EasingStyle,
  easingDirection:?Enum.EasingDirection,
  repeatCount:?int,
  reverses:?boolean,
  delayTime:?int
)
---
Creates a new tween info from
- time
  - The Duration of the tween, in Seconds
- delayTime
  - The delay before the tween starts
- repeatCount
  - The number of time the tween repeats with -1 being infinite repetition
- easingStyle
  - The style in which the ease executes
- reverses
  - Wether or not the tween will play in reverse after completion
