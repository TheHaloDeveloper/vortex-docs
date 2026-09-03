---
title: Instance
description: Shared conventions for engine-backed objects in Vortex.
---

<!-- 
Instance
Revision 1.1

Written by TheJustDare on August 30th, 2026
-->

> [!IMPORTANT]
> Vortex Studio 0.3.4 does not expose one uniform Instance method set on every
> engine-backed value. The members below describe ordinary Instance-like
> objects. Use the concrete class reference and the availability matrix on this
> page before calling a method.

## Summary

<details>
<summary><b>Properties</b></summary>
Common properties of an `Instance`-like object.
<br><br>

Properties of a `Instance`
<br>

* [Name](#name): `string`
* [Parent](#parent): `Instance | nil`

</details>

<details>
<summary><b>Methods</b></summary>

Methods of an `Instance`
<br>

* [Clone()](#clone): `Instance`
* [Destroy()](#destroy): `()`
* [FindFirstChild()](#findFirstChild): `Instance?`
* [FindFirstChildOfClass()](#findFirstChildOfClass): `Instance?`
* [GetAttribute()](#getAttribute): `any`
* [GetAttributeChangedSignal()](#getAttributeChangedSignal): `Signal`
* [GetAttributes()](#getAttributes): `{ [string]: any }`
* [GetChildren()](#getchildren): `{ Instance }`
* [GetDescendants()](#getDescendants): `{ Instance }`
* [GetPropertyChangedSignal()](#getPropertyChangedSignal): `Signal`
* [IsA](#isA): `boolean`
* [SetAttribute()](#setAttribute): `()`
* [WaitForChild()](#waitForChild): `Instance`

</details>

## Properties

### Name

The name of the `Instance`. \
Names can be used to organize the game hierarchy aswell as access an object using different methods.

```lua
local baseplate = workspace.Baseplate
local spawnLocation = baseplate:FindFirstChild("SpawnLocation")
local house = workspace["House"]
```

<br>

### Parent

The container which the `Instance` is parented to. \
An `Instance` is a **child** or is **parented** to an object when its `Parent` property is set to that object.

```lua
local part = Instance.new("Part")
part.Size = Vector3.new(5, 5, 5)
part.Parent = workspace
```

<br>

## Methods

### Clone()

Create a copy of a `Instance` and all of it's descendants.

#### Syntax
`Instance:Clone(): Instance` 

```lua
local model = workspace:FindFirstChild("Model")

local newModel = model:Clone()
newModel.Parent = workspace
```

<br>

### Destroy()

Sets the `Parent` property of the `Instance` to nil and calls `Destroy()` on all of its descendants.

#### Syntax
`Instance:Destroy(): ()`

```lua
local part = workspace.Part
part:Destroy()

print(part.Name) -- Returns "Part"

part = nil -- It is recommended to set any references to nil to avoid performance issues
```

It is important to add once `Destroy()` has been called the `Parent` property of the `Instance` cannot be changed.

<br>

### FindFirstChild()

Returns the first child found with the given name. \
For `FindFirstChild()` to work, a name of a type of `string` has to be passed. \
\
An optional second parameter can be given, whether to search for the `Instance` recursively.

#### Syntax
`Instance:FindFirstChild(name: string, recursive: boolean): Instance?`

```lua
local part = workspace:FindFirstChild("Part")

if part then
    part.Position = Vector3.new(3, 1, 4)
end
```

<br>

### FindFirstChildOfClass()

Returns the first child of a `className` equal to the given class name.

#### Syntax
`Instance:FindFirstChildOfClass(className: string): Instance?`

```lua
local light = workspace:FindFirstChildOfClass("PointLight")

if light then
    light.Brightness = 10
end
```

<br>

### GetAttribute()

Returns the value which has been assigned to a given attribute name.

#### Syntax
`Instance:GetAttribute(attribute: string): any`

```lua
local part = workspace.Part
part:SetAttribute("Points", 5)

local points = part:GetAttribute("Points")

print(points) -- Returns 5
```

<br>

### GetAttributeChangedSignal()

Returns a [Signal](https://create.playvortex.io/reference/datatypes/signal) that fires when the value of a given attribute changes.

#### Syntax
`Instance:GetAttributeChangedSignal(attribute: string): Signal`

```lua
local part = workspace.Part

part:GetAttributeChangedSignal("Points"):Connect(function()
    print("The amount of points has changed")
end)

part:SetAttribute("Points", 5)
```

<br>

### GetAttributes()

Returns a dictionary of the `Instance` attributes.

#### Syntax
`Instance:GetAttributes(): { [string]: any }`

```lua
local part = workspace.Part
local attributes = part:GetAttributes()

for name, value in attributes do
    print(name .. " has the value of " .. value)
end
```

<br>

### GetChildren()

Returns an array containing all children of the `Instance`.

#### Syntax
`Instance:GetChildren(): { Instance }`

```lua
local model = workspace.Model
local parts = model:GetChildren()

for i, part in parts do
    print(part.Name .. " is child number " .. i)
end
```

<br>

### GetDescendants()

Returns an array containing all of the descendants of the `Instance`.

#### Syntax
`Instance:GetDescendants(): { Instance }`

```lua
local model = workspace.Model
local objects = model:GetDescendants()

for i, object in objects do
    if object:IsA("Part") then
        part.Size = Vector3.new(1, 2, 3)
    end
end
```

<br>

### GetPropertyChangedSignal()

Returns a [Signal](https://create.playvortex.io/reference/datatypes/signal) that fires when the value of a given property changes.

#### Syntax
`Instance:GetPropertyChangedSignal(property: string): Signal`

```lua
local part = workspace.Part

part:GetPropertyChangedSignal("Size"):Connect(function()
    print("The size has changed")
end)

part.Size = Vector3.new(1, 6, 1)
```

<br>

### IsA()

Returns `true` if the class of the `Instance` matches the given class name.

#### Syntax
`Instance:IsA(className: string): boolean`

```lua
local model = workspace.Model
local parts = model:GetChildren()

for i, part in parts do
    if part:IsA("Part") then
        part.Size = Vector3.new(1, 1, 2)
    end
end
```

<br>

### SetAttribute()

Sets the value of a given attribute to a given value.

#### Syntax
`Instance:SetAttribute(attribute: string, value: any): ()`

```lua
local part = workspace.Part
local points = part:GetAttribute("Points")

part:SetAttribute("Points", points + 1)
```

<br>

### WaitForChild()

Returns the child of the `Instance` with the given name. \
The current thread will yield if the child does not exist, until it does. \
\
An optional second parameter can be given, after how much time in seconds should the current thread yield.

#### Syntax
`Instance:WaitForChild(name: string, timeOut: number): Instance`

```lua
local part = workspace:WaitForChild("Part")
print(part .. " was added to the Workspace")
```

<br/>

## Vortex Studio Method Availability

The following matrix records whether each member is exposed as a function on the live object.

| Runtime object | `FindFirstChild` | `FindFirstChildOfClass` | `WaitForChild` | `GetChildren` | `GetDescendants` | `Clone` | `Destroy` | `IsA` |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| [`Part`](./part.md) | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| [`Script`](./script.md) | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| [`Character`](./character.md) | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| [`Workspace`](./workspace.md) | Yes | No | Yes | Yes | No | No | No | No |
| [`ReplicatedStorage`](./replicated-storage.md) | Yes | No | Yes | Yes | No | No | No | No |
| [`Players`](./players.md) | No | No | No | No | No | No | No | No |
| [`Player`](./player.md) | No | No | No | No | No | No | No | No |
| [`Humanoid`](./humanoid.md) | No | No | No | No | No | No | No | No |

A `Players` service can still provide its class-specific `GetPlayers()` method, and a `Humanoid` can provide `IsDead()`, even though the generic methods above are absent.

These observations were made in Vortex Studio 0.3.4 and may change in later versions.
