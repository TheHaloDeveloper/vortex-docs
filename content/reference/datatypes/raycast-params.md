---
title: RaycastParams
description: Parameters used to configure a raycast operation.
---

<!-- 
RaycastParams
Revision 1

Written by Kindtracker on September 19, 2026
-->

> [!NOTE]
> `RaycastParams` is currently implemented as a table and may become a datatype in the future.

## Summary

<details>
<summary><b>Properties</b></summary>
Properties of a `RaycastParams`.
<br><br>

* [ExcludeInstances](#excludeinstances): `{Instance}?`
* [IncludeInstances](#includeinstances): `{Instance}?`
* [FilterType](#filtertype): `Enum.RaycastFilterType`
</details>

## Properties

### ExcludeInstances

> `{Instance}?`
>
> A list of instances that should be excluded from the raycast.

<br/>

### IncludeInstances

> `{Instance}?`
>
> A list of instances that should be included in the raycast.

<br/>

### FilterType

> `Enum.RaycastFilterType`
>
> Determines how the raycast filter is applied to the instances specified by `ExcludeInstances` or `IncludeInstances`.

<br/>
