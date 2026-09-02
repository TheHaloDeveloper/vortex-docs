---
title: Humanoid
description: Represents the humanoid controller in a Player Character.
---

The local player's humanoid is available as
```lua
local Players = game:GetService("Players")
local player = Players.LocalPlayer -- or Players:GetPlayers()[1] on a standard script

local character = player.Character
local humanoid = character.Humanoid
```

The character's root transform is exposed separately as a
[`HumanoidRootPart`](./humanoid-root-part.md).

## Summary

<details>
<summary><b>Properties</b></summary>

Properties of a `Humanoid`
<br>

* [ClassName](#className): `String`
* [Name](#name): `String`
* [Health](#health): `number`
* [JumpHeight](#jumpHeight): `number`
* [MaxHealth](#maxHealth): `number`
* [WalkSpeed](#walkSpeed): `number`

</details>

<details>
<summary><b>Methods</b></summary>

Methods of a `Humanoid`
<br>

* [IsDead()](#isDead): `boolean`
* [GetState()](#getState): `String`
* [TakeDamage()](#takeDamage): `()`

</details>

<details>
<summary><b>Events</b></summary>

Events of a `Humanoid`
<br>

* [Died](#died): `Signal`
* [HealthChanged](#healthChanged): `Signal`

</details>

## Properties

### ClassName

The class name of the `Humanoid`. \
This property is read only and cannot be changed.

<br>

### Name

The name of the `Humanoid`. \
This property is read only and cannot be changed.

<br>

### Health

The current health value of the `Humanoid`. 

<br>

### JumpHeight

The jump height of the `Humanoid` in studs. \
The default value is set to **7 studs**.

### MaxHealth

The maximum health value the `Humanoid` can have. \
The default value is set to a **100** max health.

<br>

## Methods

### IsDead()

Returns `true` if the `Humanoid` is dead.

#### Syntax

`Humanoid:IsDead(): boolean`

For this example to work, this code has to be placed inside a `Localscript`.

```lua
local Players = game:GetService("Players")
local player = Players.LocalPlayer

local character = player.Character
local humanoid = character.Humanoid

humanoid.Died:Connect(function()
    if humanoid:IsDead() then
   	    print(player.Name .. " has died")
	end
end)
```
<br>

### GetState()

Returns one of **4** different states based on the current `Humanoid` action. \
These actions can include `Walking`, `Jumping`, `Freefall` and `Landed`.

#### Syntax
`Humanoid:GetState(): String`

For this example to work, this code has to be placed inside a `Localscript`.

```lua
local Players = game:GetService("Players")
local player = Players.LocalPlayer

local character = player.Character
local humanoid = character.Humanoid

if humanoid:GetState() == "Freefall" then
    print("The Humanoid is now falling")
end
```

<br>

### TakeDamage()

Subtracts the given value from `Health` property of the `Humanoid`. \
Passing negative numbers will **not work** and will result in an error. \
\
This method only works on a standard [script](/content/reference/classes/script.md), attempting to call it on the client will result in an error.

#### Syntax
`Humanoid:TakeDamage(amount: number): ()`

```lua
local Players = game:GetService("Players")

local player = Players[1]
local character = player.Character
local humanoid = character.Humanoid

humanoid:TakeDamage(50)
```

<br>

## Events

### Died

> [`Signal`](/content/reference/datatypes/signal.md)
>
> `humanoid.Died`
>
> Signals that the Humanoid died.

<br/>

### HealthChanged

> [`Signal`](/content/reference/datatypes/signal.md)
>
> `humanoid.HealthChanged`
>
> Signals that the Humanoid health changed.

#### Parameters

- `health`: `Number` — the updated health value.

## Testing Notes

These observations are from Vortex Studio 0.3.4 and may differ in later
releases.

The observed character Humanoid was a specialized table with `ClassName` and
`Name` both reporting `"Humanoid"`, and `Health` and `MaxHealth` both
reporting `100`. `IsDead()` was exposed and returned `false`. `Died` and
`HealthChanged` exposed `Signal:Connect`.

Assigning `Health` or `MaxHealth` is rejected in both a `LocalScript` and a
confirmed server `Script` (`RunService:IsServer()` returned `true`). The error
still says that the value is read-only in a LocalScript and server-authoritative,
so its wording does not match the observed server behavior. Server code can now
enumerate a `Player`, read its `Character`, and obtain this `Humanoid`, but that
projection does not currently grant Health-write authority.

`WalkSpeed`, `JumpPower`, `JumpHeight`, and `UseJumpPower` read as `nil` on the
tested server-visible Humanoid projection, so their write behavior remains
unknown. `Died` and `HealthChanged` are exposed Signal references; their
delivery remains unconfirmed.

The confirmed server method surface contains `IsDead()` only. The Roblox-style
methods `TakeDamage`, state/movement control, animation, and accessory methods
all read as `nil`. Of the tested Roblox-style signals, only `Died` and
`HealthChanged` are connectable; `Jumping`, `FreeFalling`, `Running`,
`StateChanged`, `MoveToFinished`, `PlatformStanding`, `Ragdoll`, and `Seated`
all read as `nil`.

The specialized Humanoid has an opaque `__index` and `__newindex` metatable;
`IsA` was not exposed on the value itself.
