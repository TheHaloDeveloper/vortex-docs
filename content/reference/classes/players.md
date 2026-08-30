---
title: Players
description: A container that holds all players currently connected as Player objects.
---

## Summary

A service that holds every currently connected clients, as [Player](https://create.playvortex.io/reference/classes/player/) instances, which contains information about a client.

### Example

```luau
-- client

local Players = game:GetService("Players")

local every_player = Players:GetPlayers() -- gets all children whose classes are `Player`
local player = Players.LocalPlayer -- gets the current client
```

## Properties

- `Name` - the name of the service;
- `Parent` - probably the actual "game", that holds everything;
- `LocalPlayer` - only accessible in the client-side, otherwise it'll be `nil`.

## Methods

- `GetChildren(): { Instance }` - all of the children inside the service;
- `GetPlayers(): { Players }` - all of the players currently connected;
