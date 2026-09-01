---
title: Vector3
description: A three-dimensional vector
---

<!-- 
Vector3
Revision 1

Written by Kindtracker on August 28th, 2026
-->

> [!NOTE] 
> There will be more things (methods, constructors, properties, etc.) in the future.

## Summary

<details>
<summary><b>Properties</b></summary>
Properties of a `Vector3`.
<br><br>

* [X](#x): `Number`
* [Y](#y): `Number`
* [Z](#z): `Number`
* [Magnitude](#magnitude): `Number`
* [Unit](#unit): `Vector3`

</details>

<details>
<summary><b>Constants</b></summary>
Constants of a `Vector3`.
<br><br>

* [zero](#zero): `Vector3`
* [one](#one): `Vector3`
* [xAxis](#xaxis): `Vector3`
* [yAxis](#yaxis): `Vector3`
* [zAxis](#zaxis): `Vector3`

</details>

<details>
<summary><b>Constructors</b></summary>
Constructors of a `Vector3`.
<br><br>

* [new(X: `Number`, Y: `Number`, Z: `Number`)](#newx-number-y-number-z-number): `Vector3`

</details>

<details>
<summary><b>Methods</b></summary>
Methods of a `Vector3`.
<br><br>

* [Cross](#cross): `Vector3`
* [Dot](#dot): `Number`
* [Lerp](#lerp): `Vector3`

</details>

## Properties

### X

> `Number` 
>
> The X-axis component of the vector.

<br/>

### Y

> `Number` 
>
> The Y-axis component of the vector.

<br/>

### Z

> `Number` 
>
> The Z-axis component of the vector.

<br/>

### Magnitude

> `Number`
>
> The vector magnitude.

<br/>

### Unit

> `Vector3`
>
> The normalized vector.

<br/>

## Constants

### zero

> `Vector3`
>
> `Vector3.zero`
>
> The vector `(0, 0, 0)`.

<br/>

### one

> `Vector3`
>
> `Vector3.one`
>
> The vector `(1, 1, 1)`.

<br/>

### xAxis

> `Vector3`
>
> `Vector3.xAxis`
>
> The unit vector along the X axis, `(1, 0, 0)`.

<br/>

### yAxis

> `Vector3`
>
> `Vector3.yAxis`
>
> The unit vector along the Y axis, `(0, 1, 0)`.

<br/>

### zAxis

> `Vector3`
>
> `Vector3.zAxis`
>
> The unit vector along the Z axis, `(0, 0, 1)`.

<br/>

## Constructors

### new(X: `Number`, Y: `Number`, Z: `Number`)

> `Vector3` 
>
> Returns a new `Vector3` from the given components.

<br/>

## Verified runtime compatibility

In Vortex Studio 0.3.4, `Vector3.new`, unary negation, and the constants
`zero`, `one`, `xAxis`, `yAxis`, and `zAxis` were confirmed in both `Script`
and `LocalScript`. `Vector3.new(3, 4, 12)` has magnitude `13` and unit vector
approximately `(0.230769, 0.307692, 0.923077)` in both contexts.

## Methods

### Cross()

> `Vector3`
>
> `vector:Cross(other: Vector3)`
>
> Returns the cross product of `vector` and `other`.

#### Parameters

- `other`: `Vector3` — the vector to cross with.

<br/>

### Dot()

> `Number`
>
> `vector:Dot(other: Vector3)`
>
> Returns the dot product of `vector` and `other`.

#### Parameters

- `other`: `Vector3` — the vector to dot with.

<br/>

### Lerp()

> `Vector3`
>
> `vector:Lerp(other: Vector3, alpha: Number)`
>
> Returns a linear interpolation between `vector` and `other`.

#### Parameters

- `other`: `Vector3` — the target vector.
- `alpha`: `Number` — the interpolation amount, from `0` to `1`.

<br/>

## Operators

The following expressions completed successfully:

```lua
Vector3.new(1, 2, 3) + Vector3.new(1, 2, 3)
Vector3.new(1, 2, 3) - Vector3.new(1, 2, 3)
Vector3.new(1, 2, 3) * 2
Vector3.new(1, 2, 3) / 2
-Vector3.new(1, -2, 3)
```

The tested results were `(5, 7, 9)`, `(3, 3, 3)`, `(2, 4, 6)`, and `(4, 3, 2)`
respectively; unary negation returned `(-1, 2, -3)`.

The probes observed `Vector3.new(1, 0, 0):Cross(Vector3.new(0, 1, 0))`
returning `(0, 0, 1)`, `Vector3.new(1, 2, 3):Dot(Vector3.new(4, 5, 6))`
returning `32`, and interpolation from `(0, 0, 0)` to `(8, 4, 2)` at `0.25`
returning `(2, 1, 0.5)`.

## Testing Notes

The detailed Vector3 behavior above was revalidated in Vortex Studio 0.3.4 in
both Script and LocalScript. `Vector3.FromAxis` and `Vector3.FromNormalId`
remain unavailable (`nil`).
