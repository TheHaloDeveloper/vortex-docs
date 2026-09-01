---
title: StringValue
description: A detached string value container.
---

## Summary

`StringValue` is constructable in Vortex Studio 0.3.4 in both `Script` and
`LocalScript`. It stores a string `Value` and does not need a parent to be
read or written.

## Properties

### Name

> `string`

The instance name. A new value is named `StringValue`.

### Value

> `string`

A new `StringValue` starts with the empty string. Assigning and reading a
string works:

```lua
local message = Instance.new("StringValue")
message.Value = "Hello, Vortex"
print(message.Value) -- Hello, Vortex
```

## Change notifications

`Changed` and `GetPropertyChangedSignal("Value")` are present and connectable,
but changing `Value` did not invoke either callback in the tested 0.3.4
runtime. Poll `Value` when a script must observe a change.
