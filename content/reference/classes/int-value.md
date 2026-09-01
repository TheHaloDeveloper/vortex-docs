---
title: IntValue
description: A detached integer value container.
---

## Summary

`IntValue` is constructable in Vortex Studio 0.3.4 in both `Script` and
`LocalScript`. It stores a numeric `Value` and does not need a parent to be
read or written.

## Properties

### Name

> `string`

The instance name. A new value is named `IntValue`.

### Value

> `number`

A new `IntValue` starts at `0`. Assigning and reading integral values works:

```lua
local score = Instance.new("IntValue")
score.Value = 42
print(score.Value) -- 42
```

## Change notifications

`Changed` and `GetPropertyChangedSignal("Value")` are present and connectable,
but changing `Value` did not invoke either callback in the tested 0.3.4
runtime. Poll `Value` when a script must observe a change.
