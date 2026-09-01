---
title: BindableEvent
description: A partially exposed local-event instance.
---

## Runtime support

`BindableEvent` is constructable in Vortex Studio 0.3.4 in both `Script` and
`LocalScript`. It exposes an `Event` table.

However, the instance has no `Fire` method, so scripts cannot trigger that
signal. Its practical use as an in-process event bus is therefore unavailable
in the current runtime.

```lua
local event = Instance.new("BindableEvent")
print(event.Event) -- signal table
print(event.Fire)  -- nil
event:Destroy()
```
