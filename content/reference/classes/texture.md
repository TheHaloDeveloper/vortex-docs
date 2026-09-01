---
title: Texture
description: Textures allow for rendering special decals onto parts
---

<!-- 
Texture
Revision 1

Written by KingTasaz on August 28th, 2026
-->

## Summary
This page describes the editor-facing Texture concept. Texture scripting is not
currently available in the Vortex runtime; see the testing notes below. When a
texture is added to an editor-authored [`part`](./part.md), its `Face` and name
are set automatically, so six textures can cover the entire part quickly.
<br><br>

<details>
<summary><b>Properties</b></summary>
Properties of a Texture, in the order they appear on Vortex Studio.
<br><br>
<ul>
<details>
<summary><b>Texture</b></summary>

- [Face](#face): [`Enum.Face`](../datatypes/enumitem.md)
- [Texture](#texture): [`Enum.Texture`](../datatypes/enumitem.md)

</details>

</ul>
</details>


## Properties

### Face
> [`Enum.Face`](../datatypes/enumitem.md) \
\
Controls which face of the parent [`part`](./part.md) that the texture is displayed on.

<br/>

### Texture
> [`Enum.Texture`](../datatypes/enumitem.md) \
\
Sets which texture to render onto the selected face.
Currently the only options are `Inlets` or `Studs`. 

<br/>

## Testing Notes

In Vortex Studio 0.3.4, `Instance.new("Texture")`,
`Instance.new("Decal")`, and `Instance.new("SurfaceAppearance")` all fail in
both Script and LocalScript. A script-created `Part` also has no readable
`Texture`, `TextureID`, `SurfaceAppearance`, or `Decal` field.

Editor-authored texture behavior was not established by this probe, but there
is currently no confirmed script API for creating or changing textures.
