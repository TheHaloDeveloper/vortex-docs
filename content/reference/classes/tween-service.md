---
title: TweenService
description: Creates Tween objects for instance-property animation.
---

<!-- 
TweenService

Written by CNK on August 30th, 2026.
-->

## Summary

Service that is used to create a tween. A tween is a smooth interpolation between two states over a period of time. 

`TweenService` is available through `game:GetService("TweenService")`.

<details>
<summary><b>Methods</b></summary>
Methods of `TweenService`.
<br><br>

* [Create(instance: `Instance`, tweenInfo: `TweenInfo`, goals: `{[string]: any}`)](#createinstance-instance-tweeninfo-tweeninfo-goals-stringany): `Tween`

</details>

## Methods

### Create(instance: `Instance`, tweenInfo: `TweenInfo?`, goals: `{[string]: any}`)

> [`Tween`](/content/reference/datatypes/tween.md)
> 
> Returns a tween based on the given instance, tween information and goals. This can be activated with `Tween:Play()`. 
> 
> An example of the `goals` table:
> ```luau
> -- This table uses interpolatable property names as the keys
> -- and then the values are the desired value of that property.
> local goals = {
>   Position = part.Position + Vector3.new(0, 10, 0),
>   Color = Color3.fromRGB(255, 100, 0),
> }
> ```

## Testing Notes

`TweenService.Create` and its returned Tween surface were revalidated in
Vortex Studio 0.3.4.

`Create` returned a Tween in both `Script` and `LocalScript` when given an
unparented `Part`, `TweenInfo.new(0.1)`, and `{ Transparency = 0.5 }`.
