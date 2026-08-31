---
title: Remote Events
description: Send one-way messages between a client and the server.
---

Remote events send a message without waiting for a return value. Use them for notifications and action requests. Use a [Remote Function](/guides/remote-functions/) when the caller needs a response.

> Never trust values sent by a client. Check them on the server before changing shared state.

## Direction

| Member | Direction |
| --- | --- |
| `remote:FireServer(...)` | Client to server |
| `remote:FireClient(playerOrUserId, ...)` | Server to one client |
| `remote:FireAllClients(...)` | Server to every client |
| `FireServer(channel, ...)` | Client to a named server channel |
| `OnRemoteEvent(channel, callback)` | Connects a callback to a named remote channel |

Calls made from the wrong script context raise an error.

## Example

The client requests a colour change. The server checks the message before changing shared state.

```luau
-- LocalScript
FireServer("ChangeColor", "blue")
```

```luau
-- Script
local block = game:GetService("Workspace"):WaitForChild("ColorBlock")
local colors = {
    blue = Color3.fromRGB(70, 130, 255),
    red = Color3.fromRGB(235, 80, 80),
}

OnRemoteEvent("ChangeColor", function(colorName)
    if type(colorName) ~= "string" or not colors[colorName] then
        return
    end

    block.Color = colors[colorName]
end)
```

Remote payloads can contain primitive values, `Vector3`, `Color3`, lists, and maps with supported primitive keys. This build rejects Instances and CFrames.
