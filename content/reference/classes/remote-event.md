---
title: RemoteEvent
description: Sends one-way messages between client and server.
---

## Summary

`RemoteEvent` is a supported `Instance.new` target. The callable direction is enforced by the runtime.

## Methods

| Member | Context | Description |
| --- | --- | --- |
| `FireServer(...any)` | LocalScript | Sends values from the client to the server. |
| `FireClient(playerOrUserId, ...any)` | Script | Sends values to one client. The first argument must identify a Player. |
| `FireAllClients(...any)` | Script | Sends values to every client. |

Roblox-style `OnServerEvent` and `OnClientEvent` signals are not exposed by the current verified bridge. Server code can receive low-level channels through `OnRemoteEvent(channel, callback)`.

RemoteEvent also inherits the common [Instance](/reference/classes/instance/) members.

## Client example

```luau
-- LocalScript
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local remote = ReplicatedStorage:WaitForChild("RoundEvent")

remote:FireServer("Ready")
```

## Server example

```luau
-- Script
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local remote = ReplicatedStorage:WaitForChild("RoundEvent")

remote:FireAllClients("RoundStarted", 90)
```

Remote payloads support primitive values, `Vector3`, `Color3`, lists, and maps. Instances and `CFrame` values are rejected.
