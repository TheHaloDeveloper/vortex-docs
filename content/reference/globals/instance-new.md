---
title: Instance.new
description: Creates an Instance of a supported class.
---

## Constructor

### Instance.new(className: `string`, parent: `Instance?`): `Instance`

Creates an Instance whose `Name` defaults to its class name. Set the parent after configuring the object, or pass it as the second argument.

```luau
local part = Instance.new("Part")
part.Name = "Platform"
part.Size = Vector3.new(8, 1, 8)
part.Anchored = true
part.Parent = workspace
```

## Supported classes

| Category | Classes |
| --- | --- |
| Scene | `Part`, `Model`, `Folder`, `PointLight`, `SpotLight` |
| Scripts | `LocalScript`, `Script`, `ModuleScript` |
| Networking | `RemoteEvent`, `BindableEvent`, `RemoteFunction` |
| Values | `IntValue`, `StringValue` |

An unsupported class name raises an error.
