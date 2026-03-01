# PMM (Physical Memory Manager)

In an operating system, **memory allocation and management** is one of the most important responsibilities.

After initializing the **PMM**, the kernel finally understands:

- ✅ *"This RAM belongs to the kernel"*  
- ✅ *"This RAM is free to use"*  
- ✅ *"This RAM must never be touched"*  

---

# Bee Kernel Implementation

## Safe Physical Frame Allocation

When the kernel asks:

> **"Give me one physical page"**

The PMM safely returns:

> **"Here is one free physical memory frame."**

---

## Frame Release

When memory is no longer required:

> PMM informs the kernel that the memory frame can be reused.

This allows safe recycling of RAM without corruption.

---

## Memory Awareness

Using PMM awareness, the kernel knows:

- **Total RAM**
- **Used RAM**
- **Free RAM**
- **Reserved RAM**

---

# Internal Logic

## RAM Division

Physical RAM is divided into equal-sized blocks called **frames**.

Example:

- RAM divided into **4 KB frames**

---

## Bitmap Tracking System

Bee Kernel tracks memory using a bitmap.

- **1 Bit = 1 Frame**
  - `0` → Free frame
  - `1` → Used frame

This enables fast and secure allocation.

---

# Shell Integration (Bee Kernel Feature)

Bee Kernel exposes PMM information through shell commands.

### `meminfo`
Displays:
- Total RAM
- Used RAM
- Free RAM
- Reserved RAM

### `alloc`
Allocates one physical memory frame.

### `free`
Releases one allocated frame back to PMM.
