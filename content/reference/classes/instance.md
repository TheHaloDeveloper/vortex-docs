---
title: Instance
description: Shared conventions for engine-backed objects in Vortex.
---

<!-- 
Instance
Revision 1

Written by Kindtracker on August 28th, 2026
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

* [Name](#name): `String`
* [Parent](#parent): `Instance | nil`

</details>

<details>
<summary><b>Methods</b></summary>
Common methods of an `Instance`-like object.
<br><br>

* [Clone()](#clone): `Instance`
* [Destroy()](#destroy): `nil`
* [GetChildren()](#getchildren): `{ Instance }`

</details>

## Properties

### Name

> `String` 
>
> The name of the `Instance`.

<br/>

### Parent

> `Instance | nil`
>
> The instance's hierarchical parent, or `nil` when it has no parent.

<br/>

## Methods

### Clone()

> `Instance` 
>
> Create a copy of the `Instance` and return copy.

<br/>

### Destroy()

> `nil` 
>
> Destroy the `Instance` and children.

<br/>

### GetChildren()

> `{ Instance }` 
>
> Return children of the `Instance`.

<br/>

## Vortex Studio 0.3.4 method availability

The following matrix records whether each member was exposed as a function on
the live object. It verifies availability, not every edge case of the method's
behavior.

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

This is why Roblox inheritance alone is not enough to determine the available
Vortex API. A `Players` service can still provide its class-specific
`GetPlayers()` method, and a `Humanoid` can provide `IsDead()`, even though the
tested generic methods above are absent.

## Introspection limitation

Engine-backed members may be provided through metatable lookup. `pairs()` only
enumerates direct table keys, so it can omit readable properties and other
supported members. It can also reveal engine-owned keys that are not public
API. Do not use `pairs()` as a capability check; test the named member and
consult the concrete class reference.

These observations were made in Vortex Studio 0.3.4 and may change in later
versions.
