---
title: game
description: Root object used to access Vortex services.
---

`game` provides the singleton engine services available to the current script.

## Methods

### GetService(name: `string`): `Instance`

Returns the named service. An unsupported name raises an error.

```luau
local Workspace = game:GetService("Workspace")
local RunService = game:GetService("RunService")
```

## Services

| Name | Purpose |
| --- | --- |
| `Workspace` | Scene and spatial Instance hierarchy. |
| `Players` | Player collection. |
| `RunService` | Per-update execution through `Heartbeat`. |
| `ReplicatedStorage` | Instances shared with client and server scripts. |
| `StarterPlayerScripts` | Scripts copied into the player runtime. |
| `ServerScriptService` | Server-side scripts. |
| `Debris` | Delayed Instance destruction. |
| `TweenService` | Property interpolation. |
| `UserInputService` | Input state and signals. |
