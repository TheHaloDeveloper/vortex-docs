---
title: ReplicatedStorage
description: Contains instances that are loaded by both the server and the client.
---

## Summary

`ReplicatedStorage` is a container for items that should be visible to both the server and the client. Items placed here will automatically get their properties synced from the server.

<details>
<summary><b>Appearence</b></summary>
Methods of `ReplicatedStorage`.
<br><br>

</details>
<details>
<summary><b>Transform</b></summary>
Transforms of `ReplicatedStorage`.
<br><br>

</details>

## Usage

`ReplicatedStorage` should be used to store items which can be accessed by the server and client. As a result of this server-client connection, do **not** store assets that are only used by the server as they can also be modified and seen by the client maliciously.

Local scripts do not run when parented to `ReplicatedStorage`. Instead, parent it to [StarterPlayerScripts](/content/reference/classes/starter-player-scripts.md).

## Example uses for ReplicatedStorage

* Shared [models](/content/reference/classes/model.md)
* Sound effects
* Shared events