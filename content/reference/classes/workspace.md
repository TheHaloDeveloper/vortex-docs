---
title: Workspace
description: A service that holds and renders every 3D instance that players can interact with.
---

<!-- 
Instance
Revision 1.1

Written by TheJustDare on August 31st, 2026
-->

## Summary

<details>
<summary><b>Properties</b></summary>
Properties of a Workspace, in the order they appear in Vortex Studio
<br><br>

- [ClassName](#classname): `string`
- [Name](#name): `string`
</details>

<details>
<summary><b>Methods</b></summary>
Methods of `Workspace`.
<br><br>

- [FindFirstChild](#findfirstchild): [`Instance`](./instance.md) | `nil`
- [GetChildren](#getchildren): `{ Instance }`
- [WaitForChild](#waitforchild): [`Instance`](./instance.md)

</details>

## Properties

### ClassName
> `string` \
\
The runtime class name of the service.

<br/>


### Name
> `string` \
\
The service name shown by the runtime.

<br/>

## Methods

### FindFirstChild()
> [`Instance`](./instance.md) | `nil` \
\
`workspace:FindFirstChild(name: string)` \
\
Returns the first direct child with the supplied `name`, or `nil` when none is
found.

#### Parameters

- `name`: `string` — the name of the child to find.

<br/>


### GetChildren()
> `{ Instance }` \
\
Returns the direct children of `Workspace`.

<br/>


### WaitForChild()
> [`Instance`](./instance.md) \
\
`workspace:WaitForChild(name: string)` \
\
Waits for and returns a direct child with the supplied `name`.

#### Parameters

- `name`: `string` — the name of the child to wait for.


<br/>

## Testing Notes

The hierarchy observations below were revalidated in Vortex Studio 0.3.4 and
may differ in later releases.

`Raycast` is not exposed in either Script or LocalScript context in Vortex Studio
0.3.4. A temporary `Part` can be parented to `Workspace`,
and `WaitForChild` resolves it. `FindFirstChild` returns `nil` and
`GetChildren` omits it.

For existing authored children, repeated `GetChildren()` calls can return new
Lua wrapper tables for the same underlying Instance. Do not use a returned
wrapper as a persistent table key between frames; use a unique authored name or
another stable identifier instead.
