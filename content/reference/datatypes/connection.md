---
title: Connection
description: A removable connection between a Signal and a callback.
---

`Signal:Connect` and `Signal:Once` return a `Connection`.

## Properties

| Property | Type | Description |
| --- | --- | --- |
| `Connected` | `boolean` | `true` until the connection is disconnected. |

## Methods

### Disconnect(): `()`

Stops the callback from receiving later events. Calling it again has no effect. `disconnect` is a lowercase alias.

```luau
local RunService = game:GetService("RunService")
local connection

connection = RunService.Heartbeat:Connect(function()
    connection:Disconnect()
end)
```
