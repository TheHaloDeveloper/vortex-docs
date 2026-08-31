---
title: TweenService
description: Creates tweens that interpolate Instance properties over time.
---

`TweenService` is available as a global and through `game:GetService("TweenService")`. Creating a tween does not start it; call `Play()` on the returned [`Tween`](/reference/datatypes/tween/).

## Methods

### Create(instance: `Instance`, tweenInfo: `TweenInfo?`, goals: `{ [string]: any }`): [`Tween`](/reference/datatypes/tween/)

Creates a tween for `instance`. Each key in `goals` is a property name and its value is the target. If `tweenInfo` is `nil`, the defaults from [`TweenInfo.new`](/reference/globals/tween-info/) are used.

```luau
local TweenService = game:GetService("TweenService")
local part = workspace:WaitForChild("Platform")

local tween = TweenService:Create(
    part,
    TweenInfo.new(0.45, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
    {
        Position = Vector3.new(0, 8, 0),
        Color = Color3.fromRGB(80, 160, 255),
        Transparency = 0.5,
    }
)

tween.Completed:Once(function(state)
    print("Tween ended:", state)
end)

tween:Play()
```

## Interpolation

Numbers are interpolated directly. Values with a `Lerp` method, including `Vector3`, `Color3`, and `CFrame`, use that method. Other values keep their starting value until the tween reaches its end.

The supported easing styles are `Linear`, `Sine`, `Quad`, `Cubic`, `Quart`, `Quint`, `Exponential`, `Circular`, `Back`, `Elastic`, and `Bounce`. Each supports `In`, `Out`, and `InOut` directions.

## Playback

- `Play()` begins a new tween or resumes a paused one.
- `Pause()` holds a playing tween at its current position.
- `Cancel()` resets elapsed time and fires `Completed` with `Enum.PlaybackState.Cancelled`.
- Normal completion fires `Completed` with `Enum.PlaybackState.Completed`.
- A target removed from the Instance tree is dropped from active playback.

The runtime supports up to `256` active tweens at once.
