---
title: Folder
description: A general-purpose container for instances.
---

## Runtime support

`Folder` is constructable in Vortex Studio 0.3.4 in both `Script` and
`LocalScript`. It exposes the generic instance and hierarchy methods,
including `FindFirstChild`, `GetChildren`, `GetDescendants`, and
`WaitForChild`.

## Hierarchy limitation

A detached Folder cannot form an observable runtime hierarchy. Assigning a
temporary Part's `Parent` to the Folder leaves `child.Parent == folder` false;
`FindFirstChild` returns `nil`; `GetChildren()` and `GetDescendants()` return
empty tables; and `WaitForChild` does not return the Part.

Likewise, assigning the Folder's `Parent` to `Workspace` leaves parent equality
false and does not make the Folder visible through Workspace lookup or
`GetChildren()`.

Use Folders created in the editor for organization. Do not rely on a script to
create or populate a runtime Folder hierarchy.
