---
title: Introduction
description: An introduction to scripting games in Vortex Studio.
---

Vortex Studio uses Luau for gameplay scripts. The engine API provides Instances, services, datatypes, events, tasks, tweens, and client/server communication.

```luau
local Workspace = game:GetService("Workspace")
local platform = Workspace:WaitForChild("Platform")

platform.Anchored = true
platform.Color = Color3.fromRGB(92, 170, 255)
```

Start with [Your First Script](/guides/first-script/) if you have not written a Vortex script before. The [API Reference](/reference/) lists the members verified in the current build.
