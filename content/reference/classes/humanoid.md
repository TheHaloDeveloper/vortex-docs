---
title: Humanoid
description: Represents the humanoid controller in a Player Character.
---

The current player's humanoid is available as
`game:GetService("Players").LocalPlayer.Character.Humanoid` in a `LocalScript`.
In Vortex Studio 0.3.4, a server `Script` can also reach a visible player's
character through `game:GetService("Players"):GetPlayers()[1].Character`.
The character's root transform is exposed separately as a
[`HumanoidRootPart`](./humanoid-root-part.md).

## Summary

<details>
<summary><b>Properties</b></summary>
Properties of a `Humanoid`.
<br><br>

* [ClassName](#classname): `String`
* [Name](#name): `String`
* [Health](#health): `Number`
* [MaxHealth](#maxhealth): `Number`

</details>

<details>
<summary><b>Methods</b></summary>
Methods of a `Humanoid`.
<br><br>

* [IsDead](#isdead): `Boolean`

</details>

<details>
<summary><b>Signals</b></summary>
Signals of a `Humanoid`.
<br><br>

* [Died](#died): [`Signal`](/content/reference/datatypes/signal.md)
* [HealthChanged](#healthchanged): [`Signal`](/content/reference/datatypes/signal.md)

</details>

## Properties

### ClassName

> `String`
>
> The Humanoid class name, `"Humanoid"`.

<br/>

### Name

> `String`
>
> The Humanoid name.

<br/>

### Health

> `Number`
>
> The current health value.

<br/>

### MaxHealth

> `Number`
>
> The maximum health value.

<br/>

## Methods

### IsDead

> `Boolean`
>
> `humanoid:IsDead()`
>
> Returns whether the Humanoid is dead.

## Signals

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
