---
title: Signal
description: An object that runs connected functions in a specific way.
---

<!--
Signal
Revision 1.0

Written by TheJustDare on August 30th, 2026
-->

## Summary

<details>
<summary><b>Methods</b></summary>

* [Connect()](#connect): `Connection`
* [ConnectParallel()](#connectparallel): `Connection`
* [Once()](#once): `Connection`
* [Wait()](#wait): `any`
</details>

## Overview

[Signal](/content/reference/datatypes/signal.md) is a data type that is used in user-defined functions, otherwise known as **listeners**, to trigger when something happens in the game. \
 The [Signal](/content/reference/datatypes/signal.md) might also happen to pass arguments to each listener depending on which event it is.

 ## Methods

 ### Connect()

 Connects the given function and creates a new [Connection](/content/reference/datatypes/connection.md).

 ```lua
local part = workspace.Part
part:SetAttribute("Points", 5)

part:GetAttributeChangedSignal("Points"):Connect(function()
    local newPoints = part:GetAttribute("Points")

    print(newPoints) -- Returns 5
end)
 ```

<br>

### ConnectParallel()

Unlike [Connect](#connect), `ConnectParallel` runs the connected function on a different CPU thread. This is especially useful for CPU demanding tasks like terrain generation.

<br>

### Once()

Connects the given function and creates a new [Connection](/content/reference/datatypes/connection.md). \
`Once` will run the function only **once**, unlike the other methods.

```lua
local part = workspace.Part
part.Name = "Block"

part:GetPropertyChangedSignal("Name"):Once(function()
    print("The part's name has been changed!") -- This will print only after the first change
end)

task.wait(1)

part.Name = "Cube"
```

### Wait()

Yields the current thread until the `Signal` fires. \
`Wait()` will return arguments passed by the `Signal`.
