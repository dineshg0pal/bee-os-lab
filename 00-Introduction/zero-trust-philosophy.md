# Zero-Trust Philosophy

## Simple Idea

Bee Kernel follows one rule:

> **Trust nothing.**

---

## What is untrusted?

Everything.

* Apps
* Drivers
* Services
* Modules
* Even local programs

Nothing gets permission automatically.

---

## Why?

Because bugs exist.

A small bug can crash or control the whole system.

So Bee Kernel assumes:

> Something can always fail.

---

## How Bee Kernel works

```
Apps & Drivers
      ↓
Permission Check
      ↓
Secure Kernel
      ↓
Hardware
```

Access is given **only when needed**.

---

## Goal

Build a system that is:

* safer
* isolated
* controlled
* built from scratch
* good for research
