---
title: SpawnLocation
description: A special part which provides a position to load player characters at
---

<!-- 
SpawnLocation
Revision 1

Written by KingTasaz on August 28th, 2026
-->

## Summary
> [!NOTE]
> `SpawnLocation` inherits from [`part`](./part.md).

## Runtime availability

`Instance.new("SpawnLocation")` fails in both Script and LocalScript in
Vortex Studio 0.3.4. A Workspace descendant scan also found no live
`SpawnLocation` in the tested project, so its editor-facing behavior below is
not a confirmed runtime scripting surface.

<details>
<summary><b>Properties</b></summary>
Properties of a SpawnLocation, in the order they appear on Vortex Studio.
<br><br>
<ul>
<details>
<summary><b>Appearance</b></summary>

- [Color](./part.md#color): [`Color3`](../datatypes/color3.md)
- [Transparency](./part.md#transparency): `Float`
- [Material](./part.md#material): [`Enum.Material`](../datatypes/enumitem.md) <!-- not sure if this should link to enumitem.md or enum.md -->
- [Cast Shadow](./part.md#cast-shadow): `Boolean`

</details>

<details>
<summary><b>Behaviour</b></summary>

- [Anchored](./part.md#anchored): `Boolean`
- [CanCollide](./part.md#cancollide): `Boolean`
- [Truss](./part.md#truss): `Boolean`

</details>

<details>
<summary><b>Transform</b></summary>

- [Name](./part.md#name): `String`
- [Position](./part.md#position): [`Vector3`](../datatypes/vector3.md)
- [Rotation](./part.md#rotation): [`Vector3`](../datatypes/vector3.md)
- [Size](./part.md#size): [`Vector3`](../datatypes/vector3.md)

</details>

</ul>
</details>
