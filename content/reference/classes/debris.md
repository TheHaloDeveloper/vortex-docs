---
title: Debris
description: A service that allows removal of instances without yielding
---

<!--
Debris
Revision 1.1

Written by TheJustDare on August 30th, 2026
-->

## Summary

<details>
<summary><b>Methods</b></summary>

Methods of `Debris`
<br>

* [AddItem()](#additem): `()`
* [SetMaxItems()](#setmaxitems): `()`

</details>

## Overview

`Debris` is a service that allows removal of instances without yielding for objects that may lose utility after a set period of time.

## Methods

### AddItem()

Schedules removal of a given [Instance](/content/reference/classes/instance.md) within the specified time in seconds. \
For the `AddItem()` method to execute, a number has to be given as the second parameter. \
\
Any number can be passed as the lifetime, including negative numbers.

#### Syntax
`Debris:AddItem(instance: Instance, lifetime: number): ()`

```lua
local Debris = game:GetService("Debris")

local part = Instance.new("Part")
part.Parent = workspace

Debris:AddItem(part, 5)
```
<br>

### SetMaxItems()

Sets the maximum number of tracked [Instances](/content/reference/classes/instance.md) to be removed at once. \
\
If the set number is exceeded, the next objects will be automatically destroyed until the amount is less than or equal to the number.

#### Syntax
`Debris:SetMaxItems(maxItems: number): ()`

```lua
local Debris = game:GetService("Debris")
local parts = workspace.Parts

Debris:SetMaxItems(5)

for i, part in parts:GetChildren() do
    Debris:AddItem(part, 1)

    task.wait(0.5)
end
```

> [Warning!]
> As of v0.4.0 this method **does not** work. If you try to work with this method nothing will happen.


