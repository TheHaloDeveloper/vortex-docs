---
title: UserInputService
description: Reports input state and input activity.
---

`UserInputService` is returned by `game:GetService("UserInputService")`.

## Methods

### IsKeyDown(keyCode: `Enum.KeyCode`): `boolean`

Returns whether the given keyboard key is currently held.

```luau
local UserInputService = game:GetService("UserInputService")

if UserInputService:IsKeyDown(Enum.KeyCode.LeftShift) then
    print("Left Shift is held")
end
```

## Events

| Event | Type | Description |
| --- | --- | --- |
| `InputBegan` | [`Signal`](/reference/datatypes/signal/) | Fires when an input begins. |
| `InputEnded` | [`Signal`](/reference/datatypes/signal/) | Fires when an input ends. |

```luau
local UserInputService = game:GetService("UserInputService")

UserInputService.InputBegan:Connect(function()
    print("Input began")
end)

UserInputService.InputEnded:Connect(function()
    print("Input ended")
end)
```
