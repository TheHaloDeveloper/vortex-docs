---
title: Script
description: A Luau script that runs on the server.
---

## Summary

`Script` contains server-side Luau. Use it for authoritative gameplay state and for server-only remote methods.

Script is a supported `Instance.new` target and inherits the common [Instance](/reference/classes/instance/) members. No additional runtime properties are verified in the current bridge.

## Example

```luau
-- Script
local Workspace = game:GetService("Workspace")
local objective = Workspace:WaitForChild("Objective")

objective:SetAttribute("Active", true)
```
