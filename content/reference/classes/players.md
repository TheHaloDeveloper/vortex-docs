---
title: Players
description: A container that holds all players currently connected as Player objects.
---

## Summary

A service representing connected clients as
[Player](https://create.playvortex.io/reference/classes/player/) instances.

### Example

```luau
-- LocalScript

local Players = game:GetService("Players")

local everyPlayer = Players:GetPlayers()
local player = Players.LocalPlayer
```

## Properties

- `Name` - the name of the service;
- `ClassName` - the runtime class name;
- `LocalPlayer` - available in a `LocalScript`; otherwise `nil`.

## Methods

- `GetPlayers(): { Player }` - returns the currently visible player list.

`GetChildren` is not exposed by the current Vortex Players service.

## Vortex Studio 0.3.4 notes

`GetPlayers()` returns the current player in a `LocalScript`. In a confirmed
server `Script`, it also returned a list containing the live `Player` object;
that object's `Character` is readable. `LocalPlayer` remains `nil` on the
server.

The numeric connection id passed as the first `OnServerEvent` argument still
has no known public mapping back to a particular Player. Numeric/string service
indexing and the tested player lookup methods do not provide that mapping.
