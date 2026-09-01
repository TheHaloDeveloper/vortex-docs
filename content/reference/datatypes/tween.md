---
title: Tween
description: Represents an animation created by TweenService.
---

A `Tween` is created with [`TweenService:Create`](/content/reference/classes/tween-service.md#create).

## Summary

<details>
<summary><b>Properties</b></summary>
Properties of a `Tween`.
<br><br>

* [PlaybackState](#playbackstate): `Enum.PlaybackState`

</details>

<details>
<summary><b>Methods</b></summary>
Methods of a `Tween`.
<br><br>

* [Play](#play)
* [Pause](#pause)
* [Cancel](#cancel)

</details>

<details>
<summary><b>Signals</b></summary>
Signals of a `Tween`.
<br><br>

* [Completed](#completed): [`Signal`](/content/reference/datatypes/signal.md)

</details>

## Properties

### PlaybackState

> `Enum.PlaybackState`
>
> The current state of the Tween.

<br/>

## Methods

### Play

> `tween:Play()`
>
> Starts or resumes the Tween.

<br/>

### Pause

> `tween:Pause()`
>
> Pauses the Tween.

<br/>

### Cancel

> `tween:Cancel()`
>
> Cancels the Tween.

## Signals

### Completed

> [`Signal`](/content/reference/datatypes/signal.md)
>
> `tween.Completed`
>
> Fires when the Tween completes or is cancelled.

#### Parameters

- `playbackState`: `Enum.PlaybackState` — the state that ended playback.

## Testing Notes

These observations are from Vortex Studio 0.3.4.

`Play`, `Pause`, `Cancel`, `Completed`, and `PlaybackState` are exposed in both
`Script` and `LocalScript`.

For a Tween with a `0.1` second duration, `Play()` set `PlaybackState` to
`Enum.PlaybackState.Playing`, but the target property did not change and
`Completed` did not fire after waiting more than `0.2` seconds. `Cancel()` set
the state to `Enum.PlaybackState.Cancelled` and fired `Completed` once with
that same state.
