---
title: Debris
description: Schedules Instances for destruction after a delay.
---

`Debris` is available as a global and through `game:GetService("Debris")`.

## Methods

### AddItem(item: `Instance?`, lifetime: `number?`): `()`

Schedules `item:Destroy()` without yielding the current script. `lifetime` defaults to `10` seconds. Passing `nil` does nothing.

```luau
local part = Instance.new("Part")
part.Name = "TemporaryPlatform"
part.Parent = workspace

Debris:AddItem(part, 5)
```

### SetMaxItems(): `()`

Compatibility method with no effect.
