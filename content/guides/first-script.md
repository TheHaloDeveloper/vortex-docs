---
title: Your First Script
description: Learn how to make your first script in Vortex Studio.
---

<!-- 
Your first script
Revision 2

Written by RatMilk on September 1st, 2026
-->

Let's make Hello world script, create a script in ServerScriptService.
You will see:
```lua
print("Hello, world!")
```
Then playtest the game, you will see "Hello, world!" in the output. Now, let's spawn a part in Workspace.
First we need to create a part using the `Instance.new()` functions
```lua
local part = Instance.new("Part")
```
We need to put it in Workspace
```lua
part.Parent = workspace
```
We made a part! Let's change position, size, name, and color of it!
```lua
part.Name = "MyPart"
part.Size = Vector3.new(2, 2, 2)
part.Position = Vector3.new(0, 10, 0)
part.Color = Color3.fromRGB(192, 32, 12)
part.Anchored = false
```
Playtest your game and you will see a part named "MyPart" with a size of `2, 2, 2`, a red color, and not anchored.
