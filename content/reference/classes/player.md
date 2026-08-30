---
title: Player
description: An instance holding information about a connected client.
---

## Summary

Always is a children of the [Players](https://create.playvortex.io/reference/classes/players/) service, and holds information about a connected client.

### Example

```luau
-- client

local Players = game:GetService("Players")

local player = Players.LocalPlayer

print("Hello, ".. player.Name.. "!")
```

## Properties

- `Name` - the player's name;
- `Parent` - will always be [Players](https://create.playvortex.io/reference/classes/players/).

## Methods

- `GetChildren(): { Instance }` - returns a table of every children inside `Player`.
