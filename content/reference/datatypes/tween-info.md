---
title: TweenInfo
description: Information of a tween
---

<!--
Expanded by CNK (Vortex IG. CNK) on Aug 30th, 2026 based on actual code.
-->

## Summary

<details>
<summary><b>Constructors</b></summary>
Constructors of a `TweenInfo`.
<br><br>

* [new(time: `Number?`, easingStyle: `Enum.EasingStyle?`, easingDirection: `Enum.EasingDirection?`, repeatCount: `Number?`, reverses: `Boolean?`, delayTime: `Number?`)](#tweeninfonewtime-number-easingstyle-enumeasingstyle-easingdirection-enumeasingdirection-repeatcount-number-reverses-boolean-delaytime-number): `TweenInfo`

</details>

<details>
<summary><b>Properties</b></summary>
Properties of a `TweenInfo`.
<br><br>

* [Time](#time): `Number`
* [EasingStyle](/reference/globals/enum/#easingstyle): `Enum.EasingStyle`
* [EasingDirection](/reference/globals/enum/#easingdirection): `Enum.EasingDirection`
* [RepeatCount](#repeatcount): `Number`
* [Reverses](#reverses): `Boolean`
* [DelayTime](#delaytime): `Number`

</details>

## Constructors

### TweenInfo.new(time: `Number?`, easingStyle: `Enum.EasingStyle?`, easingDirection: `Enum.EasingDirection?`, repeatCount: `Number?`, reverses: `Boolean?`, delayTime: `Number?`)

> `TweenInfo`
>
> Returns a `TweenInfo` data container to be fed into [TweenService](/reference/classes/tween-service/).
> 
> Note that `time` is in seconds.
> 
> All constructor parameters are optional, so not everything has to be specified; note the following defaults:
> * `TweenInfo.Time` = `1`
> * `TweenInfo.EasingStyle` = `Enum.EasingStyle.Quad`
> * `TweenInfo.EasingDirection` = `Enum.EasingDirection.Out`
> * `TweenInfo.RepeatCount` = `0`
> * `TweenInfo.Reverses` = `false`
> * `TweenInfo.DelayTime` = `0`

<br/>

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
> 
> Note that if repeat count is `-1` it will repeat forever.

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
