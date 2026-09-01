---
title: Workspace
description: Service that holds and renders every 3D player-interactable instance.
---

<!-- 
Instance
Revision 1.1

Written by TheJustDare on August 31th, 2026
-->

## Summary

<details>
<summary><b>Properties</b></summary>
Properties of a Workspace, in the order they appear on Vortex Studio
<br><br>

- [ClassName](#classname): `String`
- [Name](#name): `String`
</details>

<details>
<summary><b>Methods</b></summary>
Methods of a `Workspace`.
<br><br>

- [FindFirstChild](#findfirstchild): [`Instance`](/content/reference/classes/instance.md) | `nil`
- [GetChildren](#getchildren): `{ Instance }`
- [WaitForChild](#waitforchild): [`Instance`](/content/reference/classes/instance.md)

</details>

## Properties

### ClassName
> `String` \
\
The runtime class name of the service.

<br/>


### Name
> `String` \
\
The service name shown by the runtime.

<br/>

## Methods

### FindFirstChild()
> [`Instance`](/content/reference/classes/instance.md) | `nil` \
\
`workspace:FindFirstChild(name: String)` \
\
Returns the first direct child with the supplied `name`, or `nil` when none is
found.

#### Parameters

- `name`: `String` — the child name to find.

<br/>


### GetChildren()
> `{ Instance }` \
\
Returns the direct children of `Workspace`.

<br/>


### WaitForChild()
> [`Instance`](/content/reference/classes/instance.md) \
\
`workspace:WaitForChild(name: String)` \
\
Waits for and returns a direct child with the supplied `name`.

#### Parameters

- `name`: `String` — the child name to wait for.


<br/>

## Testing Notes

The hierarchy observations below were revalidated in Vortex Studio 0.3.4 and
may differ in later releases.

`Raycast` is not exposed in either Script or LocalScript in Vortex Studio
0.3.4. A temporary `Part` can be parented to `Workspace`,
and `WaitForChild` resolves it. `FindFirstChild` returns `nil` and
`GetChildren` omits it.

For existing authored children, repeated `GetChildren()` calls can return fresh
Lua wrapper tables for the same underlying Instance. Do not use a returned
wrapper as a persistent table key across frames; use a unique authored name or
another stable identifier instead.
