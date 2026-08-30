---
title: RemoteEvent
description: An event that sends information between client and server.
---

<!-- 
RemoteEvent
Revision 1

Written by clride and Prouddani on August 30th, 2026
-->

## Summary
A `RemoteEvent` is an Instance that facilitates one-way communication between Client and Server through events.
For two-way communication, see [RemoteFunction](https://create.playvortex.io/reference/classes/remote-function/).

## Properties
None

## Methods
### .FireServer(`...any`)
> Send any number of arguments over this event to the server

### .FireClient(client: `Player`, `...any`)

> Send any number of arguments over this event to the client.

### .FireClientAllClients(`...any`)

> Send any number of arguments over this event to every connected client.

## Events

### .OnServerEvent(client: `Player`, `...any`)

> Receive an event sent by a client to the server.
> `Connect` receives the `Player` that called the event as its first argument and then each argument sent by `FireServer`.

## .OnClientEvent(`...any`)

> Receive an event sent by a server to a client.
> `Connect` receives each argument sent by the server.


### Example

```luau
-- server

local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Players = game:GetService("Players")

local MyRemote = ReplicatedStorage:WaitForChild("MyRemote") -- WaitForChild is very important!

-- fire to a specific player
local random_player = Players:GetChildren()[math.random(1, #Players:GetChildren())]
MyRemote:FireClient(random_player, "Message coming from the server!")

-- fire to all players
MyRemote:FireAllClients("Minions, tonight, we'll steal the moon!!!")

-- receiving data from a specific player
function reply_received(player, reply)
    print("Reply received from ".. player.Name.. ": ".. reply)
end

MyRemote.OnServerEvent:Connect(reply_received)

```

```luau
-- client

local ReplicatedStorage = game:GetService("ReplicatedStorage")

local MyRemote = ReplicatedStorage:WaitForChild("MyRemote") -- WaitForChild is very important!

function received_msg(msg)
    print("Message received: ".. msg.. ". Replying.")
    MyRemote:FireServer("Copy that.")
end

MyRemote.OnClientEvent:Connect(received_msg)
```
