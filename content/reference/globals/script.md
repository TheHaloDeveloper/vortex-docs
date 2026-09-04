---
title: script
description: Keyword representing the current script instance
---

<!-- 
script
Revision 1

Written by mezz-source on August 29th, 2026
Updated by RedSnicker on September 1th, 2026
-->

The `script` keyword can be used to access the instance of the current script.
It can be used to index nearby instances or change the properties relating to itself.

For example:
```lua
local parent = script.Parent -- Getting the part that the script is inside
parent.Color = Color3.fromRGB(255,0,0)
```

<!--
stub until scripting releases
-->
