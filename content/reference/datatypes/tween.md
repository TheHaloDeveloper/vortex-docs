---
title: Tween
description: Controls an interpolation created by TweenService.
---

[`TweenService:Create`](/reference/globals/tween-service/) returns a `Tween`. Creating one does not start playback.

## Properties

| Property | Type | Description |
| --- | --- | --- |
| `Instance` | `Instance` | Target being changed. |
| `PlaybackState` | `Enum.PlaybackState` | Current playback state. |
| `Completed` | [`Signal`](/reference/datatypes/signal/) | Fires with `Completed` after normal playback or `Cancelled` after `Cancel()`. |

## Methods

### Play(): `()`

Starts playback. Calling it after `Pause()` resumes from the paused position; calling it while already playing has no effect.

### Pause(): `()`

Pauses a playing tween. Other states are unchanged.

### Cancel(): `()`

Stops playback, resets elapsed time, sets `PlaybackState` to `Enum.PlaybackState.Cancelled`, and fires `Completed` with that state.

```luau
local TweenService = game:GetService("TweenService")
local part = workspace:WaitForChild("Platform")
local tween = TweenService:Create(part, TweenInfo.new(0.4), {
    Position = Vector3.new(0, 8, 0),
})

tween.Completed:Once(function(state)
    print(state)
end)

tween:Play()
```

A tween is removed from playback if its target no longer has a parent.
