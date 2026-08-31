---
title: Remote Functions
description: Request a value from the server and wait for its response.
---

A `RemoteFunction` handles a client-to-server request that needs a return value. `InvokeServer` yields until the server handler returns or raises an error.

> Never trust values sent by a client. Check them on the server before using them.

| Member | Description |
| --- | --- |
| `remote:InvokeServer(...)` | Calls the server from a LocalScript and returns the handler's values. |
| `remote.OnServerInvoke` | The server callback that handles the request. |

## Example

Create a `RemoteFunction` named `ItemPrice` in `ReplicatedStorage`.

```luau
-- Script
local remote = game:GetService("ReplicatedStorage"):WaitForChild("ItemPrice")
local prices = {
    sword = 250,
    shield = 175,
}

remote.OnServerInvoke = function(itemId)
    if type(itemId) ~= "string" then
        return nil
    end

    return prices[itemId]
end
```

```luau
-- LocalScript
local remote = game:GetService("ReplicatedStorage"):WaitForChild("ItemPrice")
local price = remote:InvokeServer("sword")

if price then
    print("Price:", price)
end
```

Only clients can call `InvokeServer`. The same payload restrictions as [Remote Events](/guides/remote-events/) apply.
