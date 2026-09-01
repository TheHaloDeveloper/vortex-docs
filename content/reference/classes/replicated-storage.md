---
title: ReplicatedStorage
description: Contains instances that are loaded by both the server and the client.
---

## Summary

ReplicatedStorage is a container for items that should be visible to both the
server and the client. Items placed here will automatically get their
properties synced from the server.

<details>
<summary><b>Properties</b></summary>
Properties of `ReplicatedStorage`.
<br><br>

- [ClassName](#classname): `String`
- [Name](#name): `String`

</details>

<details>
<summary><b>Methods</b></summary>
Methods of `ReplicatedStorage`.
<br><br>

- [FindFirstChild](#findfirstchild): [`Instance`](/content/reference/classes/instance.md) | `nil`
- [GetChildren](#getchildren): `{ Instance }`
- [WaitForChild](#waitforchild): [`Instance`](/content/reference/classes/instance.md)

</details>

## Parenting

Assign a `Part` by setting its `Parent` to `ReplicatedStorage`:

```luau
local ReplicatedStorage = game:GetService("ReplicatedStorage")

local part = Instance.new("Part")
part.Name = "SharedPart"
part.Parent = ReplicatedStorage
```

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
`ReplicatedStorage:FindFirstChild(name: String)` \
\
Returns the first direct child with the supplied `name`, or `nil` when none is
found.

#### Parameters

- `name`: `String` — the child name to find.

<br/>


### GetChildren()
> `{ Instance }` \
\
Returns the direct children of `ReplicatedStorage`.

<br/>


### WaitForChild()
> [`Instance`](/content/reference/classes/instance.md) \
\
`ReplicatedStorage:WaitForChild(name: String)` \
\
Waits for and returns a direct child with the supplied `name`.

#### Parameters

- `name`: `String` — the child name to wait for.

<br/>


## Testing Notes

These observations are from Vortex Studio 0.3.4 and may differ in later
releases.

A temporary `Part` can be parented to `ReplicatedStorage`, and
`WaitForChild` resolves it. `FindFirstChild` returns `nil` and `GetChildren`
omits it.
