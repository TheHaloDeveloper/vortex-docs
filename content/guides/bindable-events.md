---
title: Bindable Events
description: Local event endpoints available to scripts in the same runtime.
---

`BindableEvent` is a constructible Instance intended for communication inside one runtime. It does not send data between the client and server; use a [RemoteEvent](/guides/remote-events/) for that.

The current verified script bridge exposes the class but does not expose public bindable members. Treat it as reserved until those members are available in the API reference.
