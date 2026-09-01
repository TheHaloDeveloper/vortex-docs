---
title: Values
description: Store simple script-visible values in Vortex.
---

## Available containers

Vortex Studio 0.3.4 supports detached [`IntValue`](/content/reference/classes/int-value.md)
and [`StringValue`](/content/reference/classes/string-value.md) instances.
They start at `0` and `""` respectively, and their `Value` properties are
readable and writable in both Script and LocalScript.

```lua
local coins = Instance.new("IntValue")
coins.Value = 25

local status = Instance.new("StringValue")
status.Value = "ready"
```

`BoolValue` cannot currently be constructed. Use a Lua boolean for local
state, or an `IntValue` with a clear `0`/`1` convention when instance-backed
state is needed.

## Observing changes

The value instances expose `Changed` and
`GetPropertyChangedSignal("Value")`, but neither delivered callbacks after a
`Value` assignment in the tested runtime. Read or poll `Value` instead of
using these signals for game logic.
