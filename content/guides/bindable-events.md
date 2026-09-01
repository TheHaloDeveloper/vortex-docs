---
title: Bindable Events
description: Current BindableEvent support in Vortex Studio.
---

`BindableEvent` can be created and exposes an `Event` table in both Script and
LocalScript. The counterpart required to emit an event,
`BindableEvent:Fire(...)`, is unavailable in Vortex Studio 0.3.4.

As a result, BindableEvents cannot currently be used for script-to-script
messaging. Use a shared state mechanism or an authored
[`RemoteEvent`](/content/reference/classes/remote-event.md) when the message
must cross client/server contexts.
