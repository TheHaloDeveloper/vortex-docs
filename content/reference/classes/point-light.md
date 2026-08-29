---
title: PointLight
description: A spherical light emitting from a single point 
---

<!-- 
PointLight
Revision 1

Written by KingTasaz on August 28th, 2026
-->

## Summary
A `pointlight` must be the child of a [`part`](/content/reference/classes/part.md), and takes the position of its parent as its own.

There is currently no on/off switch for lights, but setting either the color, brightness, or range to 0 will have the desired effect.

<details>
<summary><b>Properties</b></summary>
Properties of a Pointlight, in the order they appear on Vortex Studio.
<br><br>
<ul>
<details>
<summary><b>Appearance</b></summary>

- [Color](#color): [`Color3`](/content/reference/datatypes/color3.md)
- [Brightness](#brightness): `Float`
- [Range](#range): `Float`

</details>

<details>
<summary><b>Transform</b></summary>

- [Name](#name): `String`

</details>

</ul>
</details>

## Properties

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


### Name
> `String` \
\
The name of the `pointlight`, and its label in the explorer.

<br/>


### Range
> `Float` \
\
The maximum (spherical) range that the light can reach.
This controls the drop-off of the brightness over time, but does not increase the brightness.

<br/>