---
title: RemoteEvent
description: An event that sends information between client and server.
---

<!-- 
RemoteEvent
Revision 1

Written by clride on August 30th, 2026
-->

## Summary
A `RemoteEvent` is an Instance that facilitates one-way communication between Client and Server through events.

## Properties
None

## Methods
### .FireServer(`...any`)
> Send any number of arguments over this event to the server

### .FireClient(client: `Player`, `...any`)

> Send any number of arguments over this event to the client.

### .FireClientAllClients(`...any`)

> Send any number of arguments over this event to every connected client.

## Events

### .OnServerEvent(client: `Player`, `...any`)

> Receive an event sent by a client to the server.
> `Connect` receives the `Player` that called the event as its first argument and then each argument sent by `FireServer`.

## .OnClientEvent(`...any`)

> Receive an event sent by a server to a client.
> `Connect` receives each argument sent by the server.
