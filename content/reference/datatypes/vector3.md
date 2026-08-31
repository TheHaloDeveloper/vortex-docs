---
title: Vector3
description: A three-dimensional vector.
---

`Vector3` stores three numbers and supports the usual vector operations.

## Constructor

### Vector3.new(x: `number?`, y: `number?`, z: `number?`): `Vector3`

Missing components default to `0`.

```luau
local offset = Vector3.new(0, 4, -2)
```

## Properties

| Property | Type | Description |
| --- | --- | --- |
| `X`, `Y`, `Z` | `number` | Vector components. |
| `Magnitude` | `number` | Length of the vector. |
| `Unit` | `Vector3` | Vector with the same direction and a length of `1`. A zero vector stays zero. |

## Constants

| Constant | Value |
| --- | --- |
| `Vector3.zero` | `Vector3.new(0, 0, 0)` |
| `Vector3.one` | `Vector3.new(1, 1, 1)` |
| `Vector3.xAxis` | `Vector3.new(1, 0, 0)` |
| `Vector3.yAxis` | `Vector3.new(0, 1, 0)` |
| `Vector3.zAxis` | `Vector3.new(0, 0, 1)` |

## Methods

### Dot(other: `Vector3`): `number`

Returns the dot product.

### Cross(other: `Vector3`): `Vector3`

Returns a vector perpendicular to both operands.

### Lerp(goal: `Vector3`, alpha: `number`): `Vector3`

Interpolates between this vector and `goal`. An `alpha` of `0` returns the starting vector; `1` returns the goal.

```luau
local start = Vector3.new(0, 0, 0)
local finish = Vector3.new(10, 4, 0)
local halfway = start:Lerp(finish, 0.5)
```

## Operators

`Vector3` supports `+`, `-`, unary `-`, equality, component-wise multiplication and division, multiplication by a number on either side, and division by a number on the right.
