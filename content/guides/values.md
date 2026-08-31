---
title: Values
description: Values used by properties, attributes, and remote calls.
---

Vortex scripts use Luau primitives alongside engine datatypes and Instances.

| Value | Common use |
| --- | --- |
| `boolean`, `number`, `string`, `nil` | Flags, counts, text, and missing values |
| [Vector3](/reference/datatypes/vector3/) | Positions, sizes, and directions |
| [Color3](/reference/datatypes/color3/) | RGB colors |
| [CFrame](/reference/datatypes/cframe/) | Position and rotation |
| [EnumItem](/reference/datatypes/enumitem/) | Named engine options |
| [Instance](/reference/classes/instance/) | Objects in the game hierarchy |

## Value Instances

[IntValue](/reference/classes/int-value/) stores a number. [StringValue](/reference/classes/string-value/) stores text. Read or assign their `Value` property like any other property.

## Attributes

Attributes accept `boolean`, `number`, and `string` values. Passing `nil` to `SetAttribute` removes the attribute.

## Remote values

In Vortex Studio v0.3.4, remote payloads support primitive values, Vector3, Color3, lists, and maps with primitive keys. Instances and CFrames cannot be sent through remotes. Send an identifier or numeric data instead. See [Sandbox Limits](/guides/sandbox-limits/) for the runtime guards.

## Example

```luau
local ReplicatedStorage = game:GetService("ReplicatedStorage")

local roundStatus = Instance.new("StringValue")
roundStatus.Name = "RoundStatus"
roundStatus.Value = "Waiting"
roundStatus:SetAttribute("Round", 0)
roundStatus.Parent = ReplicatedStorage
```
