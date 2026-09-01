---
title: Connection
description: Represents a callback connected to a Signal.
---

A `Connection` is returned by [`Signal:Connect`](/content/reference/datatypes/signal.md#connect)
or [`Signal:Once`](/content/reference/datatypes/signal.md#once). It can be used
to stop the callback from receiving future signal fires.

## Summary

<details>
<summary><b>Properties</b></summary>
Properties of a `Connection`.
<br><br>

* [Connected](#connected): `Boolean`

</details>

<details>
<summary><b>Methods</b></summary>
Methods of a `Connection`.
<br><br>

* [Disconnect](#disconnect)

</details>

## Properties

### Connected

> `Boolean`
>
> Whether the connection is currently active.

<br/>

## Methods

### Disconnect

> `connection:Disconnect()`
>
> Disconnects the callback. Future signal fires no longer invoke it, and
> `Connected` becomes `false`.

## Testing Notes

These observations are from Vortex Studio 0.3.4 and may differ in later
releases.

Connections are represented as tables. The lowercase `disconnect` alias is
also exposed; this reference uses the canonical `Disconnect` name.

In both Script and LocalScript, `Connected` began as `true`, a manually fired
signal delivered its callback once, and `Disconnect()` changed `Connected` to
`false` and prevented later delivery. The lowercase `disconnect()` alias has
the same effect.
