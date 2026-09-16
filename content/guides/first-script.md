title: Your First Script
description: Learn how to make a simple part that changes color randomly
---

<!-- 
Your first script
Revision 2

Written by Kindtracker on August 29th, 2026
Revisioned by RedSnicker on September 7th 2026
-->

In this guide we're gonna learn how to make a simple part that changes color randomly in Vortex Studio.
Inside your game, create a script in `ServerScriptService`

First. we need to create a new part and save it in a variable for later use.
```lua
local part = Instance.new("Part")
```

Then lets set its position and size. and then move it over to the workspace so its visible.
For this we'll use [Vector3](/reference/datatypes/vector3)
```lua
part.Parent = workspace
part.Position = Vector3.new(5,5,5)
part.Size = Vector3.new(8,8,8)
```
If we play the game now, we can see a big cube next to the spawn point.

Now lets make the cube change color randomly every 1 second.
```lua
while true do
    task.wait(1) -- Wait 1 second
    local R = math.random(0,255)
    local G = math.random(0,255)
    local B = math.random(0,255)
    part.Color = Color3.fromRGB(R, G, B)
end
```

Congrats! now you have a part that changes color randomly every second!
