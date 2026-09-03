---
title: workspace
description: Keyword representing the global Workspace root
---

<!-- 
workspace
Revision 1.1

Written by mezz-source on August 29th, 2026
-->

The `workspace` keyword represents game's root [Workspace](https://create.playvortex.io/reference/classes/workspace) service, which contains all physical models, parts, and other [Instances](https://create.playvortex.io/reference/classes/instance) that can exist inside of it.

It can be used to index specific [Instances](https://create.playvortex.io/reference/classes/instance) or to collect objects quickly, in respect to the server or client's current understanding.

> [!WARNING]
> Instances may be unavailable when loading. Make sure instances exist before accessing.
> Failure to do so may result in runtime errors.