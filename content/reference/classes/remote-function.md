---
title: RemoteFunction
description: A function that is invoked and returns values from the server to the client, and vice-versa.
---

## Summary

Differently from [RemoteEvents](https://create.playvortex.io/reference/classes/remote-event/), `RemoteFunctions` allows data to be computed inside a function call, and returned with the computed values, which means they are more flexible and overall prefered over [RemoteEvents](https://create.playvortex.io/reference/classes/remote-event/). Although `InvokeAllClients` doesn't exist, since you'd need to yield until every player has returned a value (which isn't guarenteed).

### Example

```luau
-- server

local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Players = game:GetService("Players")

local GetPiFromDigits = ReplicatedStorage:WaitForChild("GetPiFromDigits") -- WaitForChild is very important!

-- fire to a specific player
local random_player = Players:GetChildren()[math.random(1, #Players:GetChildren())]
local pi = GetPiFromDigits:InvokeClient(random_player, 5) -- calculate 5 digits of pi

print(random_player.Name.. " replied with: ".. pi);
```

```luau
-- client

local ReplicatedStorage = game:GetService("ReplicatedStorage")

local GetPiFromDigits = ReplicatedStorage:WaitForChild("GetPiFromDigits") -- WaitForChild is very important!

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

    local result = output[1].. "."
    for i = 2, #output, 1 do
        result ..= output[i]
    end

    return result
end

GetPiFromDigits.OnClientInvoke = compute_pi
```

## Methods

- `InvokeClient(player: Player, arguments: Tuple) : Tuple` - Invokes data from the server to the client
- `InvokeServer(arguments: Tuple) : Tuple` - Invokes data from the client to the server

## Events

- `OnClientInvoke(arguments: Tuple) : Tuple` - Writable method that is called on invoking from the server to the client;
- `OnServerInvoke(player: [Player](https://create.playvortex.io/reference/classes/player/), arguments: Tuple) : Tuple` - Writable method that is called when invoking from the client to the server;
