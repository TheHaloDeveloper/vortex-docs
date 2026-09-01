---
title: TweenInfo
description: Information of a tween
---

## Summary

<details>
<summary><b>Properties</b></summary>
Properties of a `TweenInfo`.
<br><br>


* [Time](#time): `Number`
* [EasingStyle](https://create.playvortex.io/reference/globals/enum/#easingstyle): `Enum`
* [EasingDirection](https://create.playvortex.io/reference/globals/enum/#easingdirection): `Enum`
* [RepeatCount](#repeatcount): `Number`
* [Reverses](#reverses): `Boolean`
* [DelayTime](#delaytime): `Number`

</details>

<details>
<summary><b>Constructors</b></summary>
Constructors of a `TweenInfo`.
<br><br>

* [new](#new): `TweenInfo`

</details>

## Properties

### Time

> `Number`
>
> Duration for the tween, in seconds.

<br/>

### EasingStyle

> `Enum.EasingStyle`
>
> Easing style for the tween.

<br/> 

### EasingDirection 

> `Enum.EasingDirection`
>
> Direction in which the tween should execute.
<br/>

### RepeatCount

> `Number`
>
> Number of times the tween repeats.

> Set `repeatCount` to `-1` to repeat forever.

<br/>

### Reverses 

> `Boolean`
>
> Whether the tween should reverse to the starting value once it reaches its target.

<br/>

### DelayTime 

> `Number`
>
> Time before the tween begins, in seconds.
<br/>

## Constructors

### new

> `TweenInfo`
>
> `TweenInfo.new(time: Number, easingStyle: Enum.EasingStyle, easingDirection: Enum.EasingDirection, repeatCount: Number, reverses: Boolean, delayTime: Number)`
>
> Creates a TweenInfo value that configures a Tween.

#### Parameters

- `time`: `Number` — the duration in seconds.
- `easingStyle`: `Enum.EasingStyle` — the easing curve.
- `easingDirection`: `Enum.EasingDirection` — the easing direction.
- `repeatCount`: `Number` — the number of repeats; `-1` repeats forever.
- `reverses`: `Boolean` — whether each repeat reverses direction.
- `delayTime`: `Number` — the delay before playback begins, in seconds.

## Testing Notes

`TweenInfo.new(0.1, Enum.EasingStyle.Linear, Enum.EasingDirection.In, 0, false, 0)`
returned a TweenInfo table in both `Script` and `LocalScript` in Vortex Studio
0.3.4. Runtime availability may differ in later releases.

`repeatCount = -1` is treated as an infinite repeat count.
