---
title: SpotLight
description: A conical light emitting from a single point 
---

<!-- 
SpotLight
Revision 1

Written by KingTasaz on August 28th, 2026
-->

## Summary
A `spotlight` must be the child of a [`part`](/content/reference/classes/part.md), and takes the position of its parent as its own.

There is currently no on/off switch for lights, but setting either the color, brightness, angle, or range to 0 will have the desired effect.

Under the `properties` tab, SpotLights visibly have Position, Rotation, and Size attributes. Position and Rotation are `read-only` and size has `no effect`. It is possible these values were left in by accident.

<details>
<summary><b>Properties</b></summary>
Properties of a SpotLight, in the order they appear on Vortex Studio.
<br><br>
<ul>
<details>
<summary><b>Appearance</b></summary>

- [Color](#color): [`Color3`](/content/reference/datatypes/color3.md)
- [Brightness](#brightness): `Float`
- [Range](#range): `Float`
- [Angle](#angle): `Float`
- [Face](#face): [`Enum.Face`](/content/reference/datatypes/enumitem.md)

</details>

<details>
<summary><b>Transform</b></summary>

- [Name](#name): `String`

</details>

</ul>
</details>

## Properties

### Angle
> `Float` \
\
The angle of the emission cone.
Smaller angles can produce sharper cutoffs, and wider angles create a softer fall off.

<br/>

### Brightness
> `Float` \
\
The emission brightness of the light. Does not affect range.

<br/>

### Color
> [`Color3`](/content/reference/datatypes/color3.md) \
\
Determines the color of the emitted light.
Darker colors have the same effect as turning off the light.

<br/>


### Face
> [`Enum.Face`](/content/reference/datatypes/enumitem.md) \
\
Controls which face of the parent [`part`](/content/reference/classes/part.md) that the light is emitted from.

<br/>


### Name
> `String` \
\
The name of the `spotlight`, and its label in the explorer.

<br/>


### Range
> `Float` \
\
The maximum (linear) range that the light can reach.
This controls the drop-off of the brightness over time, but does not increase the brightness.

<br/>