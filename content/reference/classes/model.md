---
title: Model
description: A collection of explorer items, grouped into one object
---

<!-- 
Model
Revision 1

Written by KingTasaz on August 28th, 2026
-->

## Summary
Models are a very simple way to group [`parts`](/content/reference/classes/part.md) together.
Creating a model requires at least `2` parts selected, but otherwise the second part can be deleted. Parts in a model are not truly connected, but only grouped in the explorer. Models currently have no purpose other than organization.

A model with no children is still shown in the explorer, but does not exist in the world and has no transform controls.

The basic transform tools (Move, Rotate) work more or less as expected when used on a model, except for scaling which currently is not properly supported.

<details>
<summary><b>Properties</b></summary>
Properties of a Model, in the order they appear on Vortex Studio.
<br><br>
<ul>

<details>
<summary><b>Transform</b></summary>

- [Name](#name): `String`
- [Position](#position): [`Vector3`](/content/reference/datatypes/vector3.md)

</details>

</ul>
</details>

## Properties


### Name
> `String` \
\
The name of the `model`, and its label in the explorer.

<br/>


### Position
> [`Vector3`](/content/reference/datatypes/vector3.md) \
\
The position of the `model`, in World-space.
A model's position is automatically set to the mathematical average of all its children's positions. (See [Images](#images))

<br/>

## Images
<img src="../../../images/modelCenterExample1.png" alt="Model w/ Move Tool" width="400"/>