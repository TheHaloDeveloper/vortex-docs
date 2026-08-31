---
title: TweenService
description: Creates and controls property animations.
---

## Summary

`TweenService` interpolates numeric properties and values with a `Lerp` method. It is an engine-owned service returned by `game:GetService("TweenService")`.

## Methods

| Member | Description |
| --- | --- |
| `TweenService:Create(instance: Instance, info: TweenInfo?, goals: {[string]: any}): Tween` | Creates a Tween for the target Instance and goal properties. Passing `nil` for `info` uses the TweenInfo defaults. |

The target must be an Instance and `goals` must be a table. The starting values are captured when `Play()` begins a new run.

## Tween members

| Member | Description |
| --- | --- |
| `Instance: Instance` | Target being animated. |
| `PlaybackState: Enum.PlaybackState` | Current state of the Tween. |
| `Completed: Signal` | Fires with the final playback state after completion or cancellation. |
| `Play()` | Starts a new run or resumes a paused Tween. Calling it while already playing does nothing. |
| `Pause()` | Pauses an active Tween without discarding its elapsed time. |
| `Cancel()` | Stops the Tween, resets its elapsed time, and fires `Completed` with `Enum.PlaybackState.Cancelled`. |

## TweenInfo

```luau
TweenInfo.new(
    time?,
    easingStyle?,
    easingDirection?,
    repeatCount?,
    reverses?,
    delayTime?
)
```

Defaults are 1 second, `Enum.EasingStyle.Quad`, `Enum.EasingDirection.Out`, no repeats, no reverse, and no delay. A negative repeat count repeats indefinitely.

The supported easing styles are Linear, Sine, Back, Quad, Quart, Quint, Bounce, Elastic, Exponential, Circular, and Cubic. Directions are In, Out, and InOut.

## Example

```luau
local TweenService = game:GetService("TweenService")
local Workspace = game:GetService("Workspace")
local door = Workspace:WaitForChild("Door")

local openPosition = door.Position + Vector3.new(0, door.Size.Y, 0)
local tween = TweenService:Create(
    door,
    TweenInfo.new(0.45, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
    { Position = openPosition }
)

tween.Completed:Connect(function(playbackState)
    print(playbackState)
end)

tween:Play()
```

## Runtime behavior

The runtime allows up to 256 active Tweens. A Tween is removed if its target's `Parent` becomes `nil`. Unsupported goal values remain unchanged until the final sample, when the goal is assigned.
