---
title: UserInputService
description: Provides client input signals and keyboard state.
---

## Summary

`UserInputService` is a client-only service returned by `game:GetService("UserInputService")`. Requesting it from a server script raises an error.

## Members

| Member | Description |
| --- | --- |
| `InputBegan: Signal` | Fires when an input begins. The callback arguments are not yet verified. |
| `InputEnded: Signal` | Fires when an input ends. The callback arguments are not yet verified. |
| `IsKeyDown(keyCode: Enum.KeyCode): boolean` | Returns whether the specified keyboard key is currently held. |

## Example

```luau
-- LocalScript
local UserInputService = game:GetService("UserInputService")
local shiftHeld = false

local function updateShift()
    local isDown = UserInputService:IsKeyDown(Enum.KeyCode.LeftShift)
    if isDown == shiftHeld then
        return
    end

    shiftHeld = isDown
    print(isDown and "Shift pressed" or "Shift released")
end

UserInputService.InputBegan:Connect(updateShift)
UserInputService.InputEnded:Connect(updateShift)
```
