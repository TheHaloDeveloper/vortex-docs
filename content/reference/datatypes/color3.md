---

title: Color3
description: A color value comprised of red, green, and blue components.
------------------------------------------------------------------------

<link rel="stylesheet" href="/styles/test.css">

<!-- 
Color3
Revision 1

Written by Kindtracker on August 28th, 2026
-->

> [!NOTE]
> There will be more things (methods, constructors, properties, etc.) in the future. This is based on leaks.

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
* [fromHSV(H: `Number`, S: `Number`, V: `Number`)](#fromhsvh-number-s-number-v-number): `Color3`
* [fromHex(hex: `String`)](#fromhexhex-string): `Color3`

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

### fromHSV(H: `Number`, S: `Number`, V: `Number`)

> `Color3`
>
> Returns a new `Color3` from the given values. Values range from `0` to `1`.

<br/>

### fromHex(hex: `String`)

> `Color3`
>
> Returns a new `Color3` from the given hexadecimal color value.

<br/>
