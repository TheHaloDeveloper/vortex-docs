---
title: BoolValue
description: Learn about BoolValues in Vortex Studio.
---

# Summary
`BoolValues` are [Instances](https://create.playvortex.io/guides/instances/) that store a *boolean* <sup><sub>(either `true` or `false`)</sub></sup> outside of a script, you can get it's current value by using `BoolValue.Value`.

# Properties

## .Name
  `String`
The name of the `BoolValue`, and label in the explorer.

## .Value
  `Boolean`
The `Boolean` stored inside of a `BoolValue`.

# Code Snippet

```lua
-- // Here, hasKey represents our BoolValue
local hasKey = Instance.new("BoolValue")
hasKey.Value = false
hasKey.Parent = workspace

-- // If we do have the key (hasKey.Value is true) let us in!
if hasKey.Value == true then
  print("You are allowed inside!")
else
  print("Get outta' here!")
end
```

## Expected Output
```
You are allowed inside!
```

