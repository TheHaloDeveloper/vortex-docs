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
When a texture is added to a [`part`](/content/reference/classes/part.md), its `Face` and `name` get set automatically, so adding 6 textures to cover an entire part is very quick.
<br><br>

<details>
<summary><b>Properties</b></summary>
Properties of a Texture, in the order they appear on Vortex Studio.
<br><br>
<ul>
<details>
<summary><b>Texture</b></summary>

- [Face](#face): [`Enum.Face`](/content/reference/datatypes/enumitem.md)
- [Texture](#texture): [`Enum.Texture`](/content/reference/datatypes/enumitem.md)

</details>

</ul>
</details>


## Properties

### Face
> [`Enum.Face`](/content/reference/datatypes/enumitem.md) \
\
Controls which face of the parent [`part`](/content/reference/classes/part.md) that the texture is displayed on.

<br/>

### Texture
> [`Enum.Texture`](/content/reference/datatypes/enumitem.md) \
\
Sets which texture to render onto the selected face.
Currently the only options are `Inlets` or `Studs`. 

<br/>