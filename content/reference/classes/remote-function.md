---
title: RemoteFunction
description: A function that is invoked and returns values from the server to the client, and vice-versa.
---

## Summary

Differently from [RemoteEvents](https://create.playvortex.io/reference/classes/remote-event/), `RemoteFunctions` allows data to be computed inside a function call and returned with the computed values. `InvokeAllClients` does not exist, since yielding until every player returns a value is not guaranteed.

### Example

```luau
-- server

local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Players = game:GetService("Players")

local GetPiFromDigits = ReplicatedStorage:WaitForChild("GetPiFromDigits")

-- Roblox-style targeting example; see the Vortex notes below.
local activePlayers = Players:GetPlayers()
local random_player = activePlayers[math.random(1, #activePlayers)]
local pi = GetPiFromDigits:InvokeClient(random_player, 5)

print(random_player.Name .. " replied with: " .. pi)
```

```luau
-- LocalScript

local ReplicatedStorage = game:GetService("ReplicatedStorage")
local GetPiFromDigits = ReplicatedStorage:WaitForChild("GetPiFromDigits")

function compute_pi(digits)
    -- magic
    local col = math.floor(digits * 10 / 3)
    local array = {}
    for i = 1, col, 1 do table.insert(array, 2) end
    local output = {}

    for _ = 1, digits, 1 do
        local carry = 0
        for i = col - 1, 0, -1 do
            local num = array[i] * 10 + carry
            local denom = i * 2 + 1
            arr[i] = num % denom
            carry = math.floor(num / denom)
        end

        num = arr[1] * 10 + carry
        arr[1] = num % 10
        output.append(tostring(math.floor(num / 10)))
    end

    local result = output[1] .. "."
    for i = 2, #output, 1 do
        result ..= output[i]
    end

    return result
end

GetPiFromDigits.OnClientInvoke = compute_pi
```

## Methods

- `InvokeClient(player: Player, arguments: Tuple) : Tuple` - Invokes data from
  the server to the client;
- `InvokeServer(arguments: Tuple) : Tuple` - Invokes data from the client to
  the server.

## Callbacks

- `OnClientInvoke(arguments: Tuple) : Tuple` - Writable callback invoked from
  the server to the client;
- `OnServerInvoke(senderId: Number, arguments: Tuple) : Tuple` - Writable
  callback invoked from the client to the server.

## Vortex Studio 0.3.4 notes

`InvokeServer` is exposed on the client and assigning `OnServerInvoke` succeeds
in a Script for an editor-authored remote in `ReplicatedStorage`. However,
`InvokeServer(LocalPlayer)` is rejected before delivery because Instances cannot
currently be sent through remotes. A successful primitive request/response
round trip has not yet been established.

The server-side `Players:GetChildren()` route remains unavailable. In 0.3.4,
`Players:GetPlayers()` does return visible Player objects in a server Script,
so it provides the Player target shown above in principle. `OnClientInvoke` and
`InvokeClient` delivery are still untested.
