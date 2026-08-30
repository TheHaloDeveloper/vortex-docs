---
title: Instance.new
description: Creates a new Instance of the given class
---

<!-- 
Instance.new
Revision 1

Written by Arbuzyonak on August 30th, 2026
-->

## Summary

<details>
<summary><b>Syntax</b></summary>

`Instance.new(className: string, parent: Instance?): Instance`

</details>

## Overview

`Instance.new` creates a new [`Instance`](/content/reference/classes/instance.md) of the class passed as `className`.

```lua
local part = Instance.new("Part")
print(part)            --> Part
print(part.ClassName)  --> Part
print(part.Name)       --> Part
```

## Parenting

A new instance has no parent: it exists in memory, but it is not rendered, replicated, or saved until you assign its [`Parent`](/content/reference/classes/instance.md).

Set the parent **last**, after configuring the instance, so scripts listening for new objects receive it fully configured:

```lua
local part = Instance.new("Part")
part.Name = "Platform"
part.Size = Vector3.new(8, 1, 8)
part.Position = Vector3.new(0, 10, 0)
part.Anchored = true
part.Parent = workspace
```
Or, you can optionally set the parent in the second argument when calling **Instance.new**

```lua
local part = Instance.new("Part", workspace)
part.Name = "Platform"
part.Size = Vector3.new(8, 1, 8)
part.Position = Vector3.new(0, 10, 0)
part.Anchored = true
-- NOT NEEDED: part.Parent = workspace
```
If no parent is passed in, nor set later, the Instance's parent defaults to **workspace**

## Default state

> A freshly created `Part` is unanchored, medium gray, and positioned at the world origin (`0, 0.5, 0`), with its [`Name`](#overview) defaulting to the class name. Any property you do not set yourself holds the class default.

## Notes

- Common creatable classes include [`Part`](/content/reference/classes/part.md), [`Model`](/content/reference/classes/model.md), [`Folder`](/content/reference/classes/folder.md), [`SpawnLocation`](/content/reference/classes/spawnlocation.md), [`Script`](/content/reference/classes/script.md), [`LocalScript`](/content/reference/classes/localscript.md), [`ModuleScript`](/content/reference/classes/modulescript.md), [`IntValue`](/content/reference/classes/int-value.md), [`StringValue`](/content/reference/classes/string-value.md), [`BindableEvent`](/content/reference/classes/bindable-event.md), [`RemoteEvent`](/content/reference/classes/remote-event.md), [`RemoteFunction`](/content/reference/classes/remote-function.md), [`PointLight`](/content/reference/classes/point-light.md), and [`SpotLight`](/content/reference/classes/spot-light.md).

<br/>
