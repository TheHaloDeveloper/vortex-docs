---

title: Color3
description: A color value comprised of red, green, and blue components.
---

<!-- 
Color3
Revision 1

Written by Kindtracker on August 28th, 2026
-->

> [!NOTE]
> There will be more things (methods, constructors, properties, etc.) in the future.

## Summary

<details>
<summary><b>Properties</b></summary>
Properties of a `Color3`.
<br><br>

* [R](#r): `Number`
* [G](#g): `Number`
* [B](#b): `Number`

</details>

<details>
<summary><b>Constructors</b></summary>
Constructors of a `Color3`.
<br><br>

* [new(R: `Number`, G: `Number`, B: `Number`)](#newr-number-g-number-b-number): `Color3`
* [fromRGB(R: `Number`, G: `Number`, B: `Number`)](#fromrgbr-number-g-number-b-number): `Color3`

</details>

<details>
<summary><b>Methods</b></summary>
Methods of a `Color3`.
<br><br>

* [Lerp](#lerp): `Color3`

</details>

## Properties

### R

> `Number`
>
> The red value of the color.

<br/>

### G

> `Number`
>
> The green value of the color.

<br/>

### B

> `Number`
>
> The blue value of the color.

<br/>

## Constructors

### new(R: `Number`, G: `Number`, B: `Number`)

> `Color3`
>
> Returns a new `Color3` from the given values. Values range from `0` to `1`.

<br/>

### fromRGB(R: `Number`, G: `Number`, B: `Number`)

> `Color3`
>
> Returns a new `Color3` from the given values. Values range from `0` to `255`.

<br/>

## Methods

### Lerp()

> `Color3`
>
> `color:Lerp(other: Color3, alpha: Number)`
>
> Returns a component-wise linear interpolation between `color` and `other`.

#### Parameters

- `other`: `Color3` — the target color.
- `alpha`: `Number` — the interpolation amount, from `0` to `1`.

<br/>

## Testing Notes

The previously listed `Color3.fromHSV` and `Color3.fromHex` constructors were
removed from this reference because they are not exposed in Vortex Studio
0.3.4. Runtime availability may change in later releases.
