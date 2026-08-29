---
title: Part
description: A primitive rectangular prism
---

<!-- 
Part
Revision 1

Written by KingTasaz on August 28th, 2026
-->

## Summary

<details>
<summary><b>Properties</b></summary>
Properties of a Part, in the order they appear on Vortex Studio.
<br><br>
<ul>
<details>
<summary><b>Appearance</b></summary>

- [Color](#color): [`Color3`](/content/reference/datatypes/color3.md)
- [Transparency](#transparency): `Float`
- [Material](#material): [`Enum.Material`](/content/reference/datatypes/enumitem.md) <!-- not sure if this should link to enumitem.md or enum.md -->
- [Cast Shadow](#cast-shadow): `Boolean`

</details>

<details>
<summary><b>Behaviour</b></summary>

- [Anchored](#anchored): `Boolean`
- [CanCollide](#cancollide): `Boolean`
- [Truss](#truss): `Boolean`

</details>

<details>
<summary><b>Transform</b></summary>

- [Name](#name): `String`
- [Position](#position): [`Vector3`](/content/reference/datatypes/vector3.md)
- [Rotation](#rotation): [`Vector3`](/content/reference/datatypes/vector3.md)
- [Size](#size): [`Vector3`](/content/reference/datatypes/vector3.md)

</details>

</ul>
</details>

<!-- In the future, there can be more lists of `features`(?) that a part has, such as events or functions/methods -->

## Properties

### Anchored
> `Boolean` \
\
When `true`, the given part will be unable to move via interactions with the environment. \
When `false`, the part will experience gravity and forces from other parts.

<br/>


### CanCollide
> `Boolean` \
\
Determines whether the `part` is given physics collisions, or whether it can phase through other parts. \
\
**Note:** A `part` cannot be unanchored while collision is disabled.

<br/>


### Cast Shadow
> `Boolean` \
\
Controls whether or not the `part` will cast a shadow.
This can be used to save performance with part's whose shadows cannot be seen, or for glass parts which realistically would not create a shadow.

<br/>


### Color
> [`Color3`](/content/reference/datatypes/color3.md) \
\
Determines the visible color of the `part`.
Will also affect the part's [`Material`]() color.

<br/>


### Material
> [`Enum.Material`](/content/reference/datatypes/enumitem.md) \
\
Determines which `Material` type to apply when rendering the `part`.
Currently this has no effect other than visual.

<br/>


### Name
> `String` \
\
The name of the `part`, and its label in the explorer.

<br/>


### Position
> [`Vector3`](/content/reference/datatypes/vector3.md) \
\
The position of the `part`, in World-space.

<br/>


### Rotation
> [`Vector3`](/content/reference/datatypes/vector3.md) \
\
The rotation of the `part` along each axis.

<br/>


### Size
> [`Vector3`](/content/reference/datatypes/vector3.md) \
\
The size of the `part` in each dimension (width, height, depth).

<br/>


### Transparency
> `Float` \
\
Sets the `transparency` of the part from `0` (opaque) to `1` (invisible).
When drawing shadows, all parts are treated as opaque regardless of their `transparency`. Unless it is set to `1`, where the part does not render at all.

<br/>


### Truss
> `Boolean` \
\
If a `part` is a truss part, then the `Player` is able to climb the part by walking up to it. It is recommened to keep truss parts anchored, as they otherwise produce unpredictable effects.

<br/>