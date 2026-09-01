---
title: Instance
description: Instance is the base class for all classes in Vortex engine
---

<!-- 
Instance
Revision 1

Written by Kindtracker on August 28th, 2026
-->

> [!NOTE] 
> There will be more things (methods, constructors, properties, etc) in the future. This is based on leaks and common sense.

## Summary

<details>
<summary><b>Properties</b></summary>
Properties of a `Instance`.
<br><br>

* [Name](#name): `String`
* [Parent](#parent): `Instance | nil`

</details>

<details>
<summary><b>Methods</b></summary>
Methods of a `Instance`.
<br><br>

* [Clone()](#clone): `Instance`
* [Destroy()](#destroy): `nil`
* [GetChildren()](#getchildren): `{ Instance }`

</details>

## Properties

### Name

> `String` 
>
> The name of the `Instance`.

<br/>

### Parent

> `Instance | nil`
>
> The instance's hierarchical parent, or `nil` when it has no parent.

<br/>

## Methods

### Clone()

> `Instance` 
>
> Create a copy of the `Instance` and return copy.

<br/>

### Destroy()

> `nil` 
>
> Destroy the `Instance` and children.

<br/>

### GetChildren()

> `{ Instance }` 
>
> Return children of the `Instance`.

<br/>
