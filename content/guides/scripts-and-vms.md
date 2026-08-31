---
title: Scripts and VMs
description: How gameplay scripts and the Studio executor run Luau.
---

Vortex runs gameplay code on the server or a client, depending on the script type.

## Script types

- [`Script`](/reference/classes/script/) runs on the server.
- [`LocalScript`](/reference/classes/localscript/) runs on a client.
- [`ModuleScript`](/reference/classes/modulescript/) contains reusable Luau code.

`UserInputService` is client-only, Humanoid health writes are server-authoritative, and remote methods reject calls in the wrong direction. See [Client and Server](/guides/client-server/).

## Execution

Scripts use cooperative coroutines. A coroutine keeps control until it returns or yields. `task.wait` and `Signal:Wait` yield; `InvokeServer` yields until the server responds.

```luau
-- Script
local button = game:GetService("Workspace"):WaitForChild("Button")

button.Touched:Connect(function(touchingPart)
    button:SetAttribute("PressedBy", touchingPart.Name)
    task.wait(0.25)
    button:SetAttribute("PressedBy", nil)
end)
```

See [Tasks](/guides/tasks/) for the scheduling functions.

## Studio executor

The Studio Luau panel is a separate, bounded executor for short inspection and tooling snippets. It queues one snippet at a time. Calls to `print` and `warn`, along with runtime errors, appear in its console.

Gameplay code belongs in Script, LocalScript, or ModuleScript instances. The executor's source, memory, time, and console limits are listed under [Sandbox Limits](/guides/sandbox-limits/).
