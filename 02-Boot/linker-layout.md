🔗 Linker Layout
What is it?

The Linker Layout defines how your kernel’s code, data, and user programs are arranged in memory.
Think of it as the “blueprint” for memory organization.

Bee Kernel Implementation

Uses a custom linker script (user.ld)

Key memory regions:

.text → kernel and user code

.rodata → read-only data (constants, strings)

.data → initialized variables

.bss → uninitialized variables

Sets entry point: _start → first instruction executed in user space

Quick Notes

Ensures kernel and user programs are at correct memory addresses

Helps prevent memory overlap and triple faults

A clean layout makes debugging and paging easier
