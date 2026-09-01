---
title: Remote Functions
description: Current RemoteFunction support and limitations in Vortex.
---

## Current support

An editor-authored [`RemoteFunction`](/content/reference/classes/remote-function.md)
in `ReplicatedStorage` exposes `InvokeServer` to a LocalScript. A server Script
can assign `OnServerInvoke`.

Instance arguments are not supported: invoking with `LocalPlayer` fails before
delivery with an "Instances cannot be sent" runtime error. A successful
primitive request/response round trip has not yet been established in Vortex
Studio 0.3.4.

## Practical guidance

Do not use RemoteFunctions for required gameplay paths yet. Prefer an
editor-authored [`RemoteEvent`](/content/reference/classes/remote-event.md)
with primitive payloads when one-way client-to-server communication is enough.
RemoteEvent delivery has been observed; its server sender value is a numeric
identifier, not a Player object.
