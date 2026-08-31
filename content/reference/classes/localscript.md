---
title: LocalScript
description: A Luau script that runs for a client.
---

## Summary

`LocalScript` contains client-side Luau. Use it for input and other behavior that belongs to the local player. Server-authoritative state must still be checked and changed by a server `Script`.

`LocalScript` is a supported `Instance.new` target and inherits the common [Instance](/reference/classes/instance/) members. No additional runtime properties are verified in the current bridge.

## Example

```luau
-- LocalScript
local UserInputService = game:GetService("UserInputService")

UserInputService.InputBegan:Connect(function()
    if UserInputService:IsKeyDown(Enum.KeyCode.Space) then
        print("Space pressed")
    end
end)
```
