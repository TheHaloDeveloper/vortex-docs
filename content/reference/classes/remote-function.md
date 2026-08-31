---
title: RemoteFunction
description: Sends a client request to the server and waits for a response.
---

## Summary

`RemoteFunction` is a supported `Instance.new` target. The current bridge exposes client-to-server invocation only.

## Members

| Member | Context | Description |
| --- | --- | --- |
| `InvokeServer(...any): ...any` | LocalScript | Sends a request to the server and yields until a response arrives. |
| `OnServerInvoke: function?` | Script | Callback that handles an invocation and returns its response values. |

`InvokeClient`, `OnClientInvoke`, and `InvokeAllClients` are not exposed by the current verified bridge.

RemoteFunction also inherits the common [Instance](/reference/classes/instance/) members.

## Server example

```luau
-- Script
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local getPrice = ReplicatedStorage:WaitForChild("GetPrice")
local prices = { Sword = 250, Shield = 175 }

getPrice.OnServerInvoke = function(itemName)
    return prices[itemName]
end
```

## Client example

```luau
-- LocalScript
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local getPrice = ReplicatedStorage:WaitForChild("GetPrice")

local price = getPrice:InvokeServer("Sword")
print(price)
```

Remote payloads support primitive values, `Vector3`, `Color3`, lists, and maps. Instances and `CFrame` values are rejected.
