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


## Example

```luau
-- server

local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Players = game:GetService("Players")
local MyRemote = ReplicatedStorage:WaitForChild("MyRemote") -- WaitForChild is important.

-- The server can enumerate Players in 0.3.4, but FireClient delivery is still
-- unconfirmed, so this Roblox-style targeting block remains illustrative:
-- local activePlayers = Players:GetPlayers()
-- local random_player = activePlayers[math.random(1, #activePlayers)]
-- MyRemote:FireClient(random_player, "Message coming from the server!")
-- MyRemote:FireAllClients("Minions, tonight, we'll steal the moon!!!")

-- `senderId` is a numeric connection identifier in Vortex, not a Player.
local function reply_received(senderId, reply)
    print("Reply received from connection " .. senderId .. ": " .. reply)
end

MyRemote.OnServerEvent:Connect(reply_received)
```

```luau
-- LocalScript

local ReplicatedStorage = game:GetService("ReplicatedStorage")
local MyRemote = ReplicatedStorage:WaitForChild("MyRemote")

function received_msg(msg)
    print("Message received: " .. msg .. ". Replying.")
    MyRemote:FireServer("Copy that.")
end

MyRemote.OnClientEvent:Connect(received_msg)
```


## Vortex Studio 0.3.4 notes

- `FireServer` to `OnServerEvent` was confirmed for an editor-authored remote
  in `ReplicatedStorage`.
- Script-created remotes parented into `ReplicatedStorage` were visible to the
  client but did not dispatch to the server handler.
- `FireClient`, `FireAllClients`, and `OnClientEvent` are exposed, but their
  delivery has not yet been established.
- The server can enumerate Player objects through `Players:GetPlayers()`, but
  cannot map `senderId` to a specific Player, Character, or Humanoid. Normal
  Roblox-style targeting of the caller therefore does not currently apply.
- Instances, including `LocalPlayer` and the character, cannot be sent as
  remote arguments.
