---
title: Script
description: An editor-authored server execution asset.
---

## Runtime support

`Script` can be constructed in Vortex Studio 0.3.4 in both `Script` and
`LocalScript` contexts. The temporary instance exposes its `ClassName` and
`Name`, but `Source`, `Disabled`, and `RunContext` read as `nil`.

`Source` is not settable. A runtime-created Script therefore cannot be given
code and cannot become an executable server script. Assigning its `Parent` to
[`ServerScriptService`](/content/reference/classes/server-script-service.md)
does not establish an observable service child.

Use an editor-authored Script to run server code. Within one, the global
`script` refers to its current Script instance.
