---
title: CFrame
description: A 3D position and orientation.
---

`CFrame` combines a position with a rotation. Angles are measured in radians.

## Constructors

| Constructor | Description |
| --- | --- |
| `CFrame.new()` | Identity transform. |
| `CFrame.new(position: Vector3)` | Position with no rotation. |
| `CFrame.new(x: number, y: number, z: number)` | Position with no rotation. |
| `CFrame.new(position: Vector3, target: Vector3, up: Vector3?)` | Position facing `target`. |
| `CFrame.new(x, y, z, qx, qy, qz, qw)` | Position and quaternion rotation. |
| `CFrame.new(x, y, z, r00, r01, r02, r10, r11, r12, r20, r21, r22)` | Position and rotation matrix. |
| `CFrame.lookAt(position, target, up?)` | Position facing `target`; `up` defaults to `Vector3.yAxis`. |
| `CFrame.fromMatrix(position, right, up, back)` | Transform from basis vectors. |
| `CFrame.Angles(rx, ry, rz)` | XYZ Euler rotation. |
| `CFrame.fromEulerAnglesXYZ(rx, ry, rz)` | XYZ Euler rotation. |
| `CFrame.fromEulerAnglesYXZ(rx, ry, rz)` | YXZ Euler rotation. |
| `CFrame.fromOrientation(rx, ry, rz)` | Alias of `fromEulerAnglesYXZ`. |
| `CFrame.fromAxisAngle(axis, angle)` | Rotation around an axis. |

```luau
local origin = Vector3.new(0, 5, 0)
local target = Vector3.new(0, 5, -10)
local facingTarget = CFrame.lookAt(origin, target)
```

## Properties

| Property | Type | Description |
| --- | --- | --- |
| `Position`, `p` | `Vector3` | Position component. |
| `Rotation` | `CFrame` | Rotation with its position reset to zero. |
| `X`, `Y`, `Z` | `number` | Position components. |
| `LookVector` | `Vector3` | Forward direction. |
| `RightVector`, `XVector` | `Vector3` | Right direction. |
| `UpVector`, `YVector` | `Vector3` | Up direction. |
| `ZVector` | `Vector3` | Back direction. |

`CFrame.identity` is the identity transform.

## Methods

| Method | Returns | Description |
| --- | --- | --- |
| `Inverse()` | `CFrame` | Inverse transform. |
| `ToWorldSpace(cframe)` | `CFrame` | Applies this transform to another `CFrame`. |
| `ToObjectSpace(cframe)` | `CFrame` | Expresses another `CFrame` relative to this one. |
| `PointToWorldSpace(vector)` | `Vector3` | Transforms a point into world space. |
| `PointToObjectSpace(vector)` | `Vector3` | Transforms a point into object space. |
| `VectorToWorldSpace(vector)` | `Vector3` | Rotates a direction into world space. |
| `VectorToObjectSpace(vector)` | `Vector3` | Rotates a direction into object space. |
| `GetComponents()` | `12 numbers` | Returns position followed by the 3×3 rotation matrix. |
| `ToEulerAnglesXYZ()` | `3 numbers` | Returns XYZ Euler angles. |
| `ToEulerAnglesYXZ()` | `3 numbers` | Returns YXZ Euler angles. |
| `ToOrientation()` | `3 numbers` | Alias of `ToEulerAnglesYXZ`. |
| `Lerp(goal, alpha)` | `CFrame` | Interpolates position and rotation toward `goal`. |

`components`, `toEulerAnglesXYZ`, and `toEulerAnglesYXZ` are lowercase aliases of their corresponding methods.

```luau
local rotated = CFrame.Angles(0, math.rad(90), 0)
local worldPoint = rotated:PointToWorldSpace(Vector3.new(0, 0, -4))
```

## Operators

- `a * b` composes two `CFrame` values.
- `cframe * vector` transforms a point.
- `cframe + vector` and `cframe - vector` offset the position without changing rotation.
- `==` compares both position and rotation.
