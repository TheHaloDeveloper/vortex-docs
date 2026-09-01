---
title: Instances
description: Learn about Instances in Vortex Studio.
---

<!--
Written by ElectroTato on the 30th of August, 2026
-->

# Summary

`Instances` are like the basic building blocks for every object in your game, there are several types of `Instances`, each having different [`Properties`](https://create.playvortex.io/guides/properties/) and unique quirks!

You can create a new `Instance` using the [`Instance.new`](https://create.playvortex.io/reference/globals/instance-new/) method in a script, by passing in the `ClassName` of the `Instance` as the first argument.

## Inspecting members

Some engine-backed objects, including the Character projection, expose properties and methods through metatable lookup. Because of this, iterating over an object with `pairs()` does not list its complete API. Use the class reference to find supported members instead.

The tested Vortex Studio 0.3.4 Character projection does not expose the Roblox `GetFullName()` or `FindFirstChildWhichIsA()` methods.
