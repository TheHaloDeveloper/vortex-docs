---
title: Instances
description: Learn about Instances in Vortex Studio.
---

<!--
Written by ElectroTato on the 30th of August, 2026
-->

# Summary

`Instances` are the basic building blocks for objects in a game. Each concrete class has its own [`Properties`](https://create.playvortex.io/guides/properties/) and methods.

You can create a new `Instance` using the [`Instance.new`](https://create.playvortex.io/reference/globals/instance-new/) method in a script, by passing in the `ClassName` of the `Instance` as the first argument.

Vortex does not currently expose one universal base API on every engine-backed value. For example, `Part` exposes common hierarchy methods while `Player` and
`Humanoid` do not. Check the concrete class reference before using a method. The [Instance reference](../reference/classes/instance.md) contains the tested
Vortex Studio 0.3.4 availability matrix.
