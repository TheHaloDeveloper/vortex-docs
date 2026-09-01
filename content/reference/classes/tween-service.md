---
title: TweenService
description: Creates Tween objects for instance-property animation.
---

`TweenService` is available through `game:GetService("TweenService")`.

## Summary

<details>
<summary><b>Methods</b></summary>
Methods of `TweenService`.
<br><br>

* [Create](#create): [`Tween`](/content/reference/datatypes/tween.md)

</details>

## Methods

### Create

> [`Tween`](/content/reference/datatypes/tween.md)
>
> `TweenService:Create(instance: Instance, tweenInfo: TweenInfo, propertyTable: table)`
>
> Creates a Tween targeting the supplied properties of `instance`.

#### Parameters

- `instance`: `Instance` — the object whose properties the Tween targets.
- `tweenInfo`: `TweenInfo` — the animation configuration.
- `propertyTable`: `table` — property names mapped to their target values.

## Testing Notes

`TweenService.Create` and its returned Tween surface were revalidated in
Vortex Studio 0.3.4.

`Create` returned a Tween in both `Script` and `LocalScript` when given an
unparented `Part`, `TweenInfo.new(0.1)`, and `{ Transparency = 0.5 }`.
