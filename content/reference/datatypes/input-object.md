---
title: InputObject
description: Reserved input type name in the current runtime.
---

`InputObject` is present as a runtime type name, but its fields and constructors are not exposed by the current verified Luau bridge.

`UserInputService.InputBegan` and `InputEnded` are available as Signals. Their callback arguments are not yet verified, so code should not depend on Roblox `InputObject` fields such as `KeyCode`, `UserInputType`, or `Delta`.

Use `UserInputService:IsKeyDown()` when current keyboard state is enough:

```luau
local UserInputService = game:GetService("UserInputService")

print(UserInputService:IsKeyDown(Enum.KeyCode.Space))
```

See [UserInputService](/reference/classes/user-input-service/) for the verified members.
