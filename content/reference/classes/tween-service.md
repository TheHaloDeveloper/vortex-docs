---
title: TweenService
description: A service that can be used to smoothly interpolate properties of instances.
---

<!-- 
Workspace

Written by CNK on August 30th, 2026.
-->

## Summary

Service that is used to create a tween. A tween is a smooth interpolation between two states over a period of time. 

Can be easily referenced with `TweenService` in code.

<details>
<summary><b>Methods</b></summary>
Methods of `TweenService`.
<br><br>

* [Create(instance: `Instance`, tweenInfo: `TweenInfo`, goals: `{[string]: any}`)](#createinstance-instance-tweeninfo-tweeninfo-goals-stringany): `Tween`

</details>

## Methods

### Create(instance: `Instance`, tweenInfo: `TweenInfo?`, goals: `{[string]: any}`)

> `Tween`
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
> 
> Reference [Tween](/reference/datatypes/tween/) for more information on how to use it after construction.