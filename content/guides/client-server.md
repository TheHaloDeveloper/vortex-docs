---
title: Client and Server
description: Decide which side should run a script and own a game-state change.
---

Vortex games run server code and a separate client for each player.

## Server

A [`Script`](/reference/classes/script/) runs on the server. The server owns shared and trusted state, including game rules, purchases, damage, and character health.

## Client

A [`LocalScript`](/reference/classes/localscript/) runs on a player's device. Use it for input and other work that belongs to that player.

## Keep the server authoritative

Client messages are requests, not proof that an action is valid. Check their types and game rules before changing server state.

```luau
-- Script
local allowedItems = {
    sword = true,
}

OnRemoteEvent("BuyItem", function(itemId)
    if type(itemId) ~= "string" or not allowedItems[itemId] then
        return
    end

    -- Check the player's balance and grant the item here.
end)
```

See [Remote Events](/guides/remote-events/) and [Remote Functions](/guides/remote-functions/) for client/server communication.
