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

- [Color](#color): [`Color3`](../datatypes/color3.md)
- [Transparency](#transparency): `Float`
- [Material](#material): [`Enum.Material`](../datatypes/enumitem.md) <!-- not sure if this should link to enumitem.md or enum.md -->
- [Cast Shadow](#cast-shadow): `Boolean`

</details>

<details>
<summary><b>Behaviour</b></summary>

- [Anchored](#anchored): `Boolean`
- [CanCollide](#cancollide): `Boolean`
- [ClassName](#classname): `String`
- [Parent](#parent): [`Instance`](/content/reference/classes/instance.md) | `nil`
- [Truss](#truss): `Boolean`

</details>

<details>
<summary><b>Transform</b></summary>

- [CFrame](#cframe): [`CFrame`](../datatypes/cframe.md)
- [Name](#name): `String`
- [Position](#position): [`Vector3`](../datatypes/vector3.md)
- [Rotation](#rotation): [`Vector3`](../datatypes/vector3.md)
- [Size](#size): [`Vector3`](../datatypes/vector3.md)
- [Orientation](#orientation): [`Vector3`](../datatypes/vector3.md)

</details>

</ul>
</details>

<details>
<summary><b>Methods</b></summary>
<br>

- [Clone](#clone): `Part`
- [Destroy](#destroy): `nil`
- [FindFirstChild](#findfirstchild): [`Instance`](/content/reference/classes/instance.md) | `nil`
- [FindFirstChildOfClass](#findfirstchildofclass): [`Instance`](/content/reference/classes/instance.md) | `nil`
- [GetAttribute](#getattribute): `Variant` | `nil`
- [GetAttributeChangedSignal](#getattributechangedsignal): [`Signal`](/content/reference/datatypes/signal.md)
- [GetAttributes](#getattributes): `{ [String]: Variant }`
- [GetChildren](#getchildren): `{ Instance }`
- [GetDescendants](#getdescendants): `{ Instance }`
- [GetPropertyChangedSignal](#getpropertychangedsignal): [`Signal`](/content/reference/datatypes/signal.md)
- [IsA](#isa): `Boolean`
- [SetAttribute](#setattribute): `nil`
- [WaitForChild](#waitforchild): [`Instance`](/content/reference/classes/instance.md)

</details>

<details>
<summary><b>Events</b></summary>
<br>

- [Changed](#changed): [`Signal`](/content/reference/datatypes/signal.md)
- [Touched](#touched): [`Signal`](/content/reference/datatypes/signal.md)
- [TouchEnded](#touchended): [`Signal`](/content/reference/datatypes/signal.md)
</details>

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


### CFrame
> [`CFrame`](/content/reference/datatypes/cframe.md) \
\
Sets the position and rotation of the `part` as a single transform.

<br/>


### ClassName
> `String` \
\
The runtime class name of the `part`.

<br/>


### Cast Shadow
> `Boolean` \
\
Controls whether or not the `part` will cast a shadow.
This can be used to save performance with part's whose shadows cannot be seen, or for glass parts which realistically would not create a shadow.

<br/>


### Color
> [`Color3`](../datatypes/color3.md) \
\
Determines the visible color of the `part`.
Will also affect the part's [`Material`]() color.

<br/>


### Material
> [`Enum.Material`](../datatypes/enumitem.md) \
\
Determines which `Material` type to apply when rendering the `part`.
Currently this has no effect other than visual.

<br/>


### Name
> `String` \
\
The name of the `part`, and its label in the explorer.

<br/>


### Orientation
> [`Vector3`](../datatypes/vector3.md) \
\
The rotation of the `part` in degrees along each axis.

<br/>


### Parent
> [`Instance`](/content/reference/classes/instance.md) | `nil` \
\
The containing `Instance` of the `part`, or `nil` when it has no parent.

<br/>


### Position
> [`Vector3`](../datatypes/vector3.md) \
\
The position of the `part`, in World-space.

<br/>


### Rotation
> [`Vector3`](../datatypes/vector3.md) \
\
The rotation of the `part` along each axis.

<br/>


### Size
> [`Vector3`](../datatypes/vector3.md) \
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

## Methods

### Clone()
> `Part` \
\
Creates and returns a copy of the `part`.

<br/>


### Destroy()
> `nil` \
\
Destroys the `part`.

<br/>


### FindFirstChild()
> [`Instance`](/content/reference/classes/instance.md) | `nil` \
\
`part:FindFirstChild(name: String)` \
\
Returns the first direct child with the supplied `name`, or `nil` when none is
found.

<br/>


### FindFirstChildOfClass()
> [`Instance`](/content/reference/classes/instance.md) | `nil` \
\
`part:FindFirstChildOfClass(className: String)` \
\
Returns the first direct child whose class matches `className`, or `nil` when
none is found.

<br/>


### GetAttribute()
> `Variant` | `nil` \
\
`part:GetAttribute(name: String)` \
\
Returns the value stored under the supplied attribute `name`.

<br/>


### GetAttributeChangedSignal()
> [`Signal`](/content/reference/datatypes/signal.md) \
\
`part:GetAttributeChangedSignal(name: String)` \
\
Returns an event associated with changes to the supplied attribute `name`.

<br/>


### GetAttributes()
> `{ [String]: Variant }` \
\
Returns a table containing the `part` attributes.

<br/>


### GetChildren()
> `{ Instance }` \
\
Returns the direct children of the `part`.

<br/>


### GetDescendants()
> `{ Instance }` \
\
Returns the descendants of the `part`.

<br/>


### GetPropertyChangedSignal()
> [`Signal`](/content/reference/datatypes/signal.md) \
\
`part:GetPropertyChangedSignal(property: String)` \
\
Returns an event associated with changes to the supplied property.

<br/>


### IsA()
> `Boolean` \
\
`part:IsA(className: String)` \
\
Returns whether the `part` is an instance of `className` or one of its
ancestor classes.

<br/>


### SetAttribute()
> `nil` \
\
`part:SetAttribute(name: String, value: Variant | nil)` \
\
Sets the attribute `name` to `value`. Passing `nil` clears the attribute.

<br/>


### WaitForChild()
> [`Instance`](/content/reference/classes/instance.md) \
\
`part:WaitForChild(name: String)` \
\
Waits for and returns a direct child with the supplied `name`.

<br/>

## Events

### Changed
> [`Signal`](/content/reference/datatypes/signal.md) \
\
An event associated with changes to the `part`.

<br/>


### Touched
> [`Signal`](/content/reference/datatypes/signal.md) \
\
An event associated with physical contact with the `part`.

<br/>


### TouchEnded
> [`Signal`](/content/reference/datatypes/signal.md) \
\
An event associated with the end of physical contact with the `part`.

<br/>

## Testing Notes

These observations are from Vortex Studio 0.3.4 and may differ in later
releases.

> [!WARNING]
> After `child.Parent = part` succeeds, `child.Parent == part` is `false`.
> `WaitForChild(childName)` resolves the child, but `FindFirstChild`,
> `FindFirstChildOfClass`, `GetChildren`, and `GetDescendants` do not expose
> it.

`Changed`, `GetPropertyChangedSignal`, and `GetAttributeChangedSignal` expose
connectable events, but changing the corresponding property or attribute does
not deliver callbacks. `Touched` and `TouchEnded` are connectable; their event
delivery has not been established.

> [!NOTE]
> A server Script can read a player's
> [`Character.HumanoidRootPart`](./humanoid-root-part.md), but assigning its
> current `Position` or `Size` is rejected as client-side, server-authoritative
> character state. This restriction applies to the live character root part; it
> does not change the tested behavior of ordinary script-created Parts.
