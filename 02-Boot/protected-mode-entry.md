🛡️ Protected Mode Entry
What is Protected Mode?

Protected Mode is the CPU mode where we can use:

32-bit addressing

Virtual memory (paging)

Hardware-level protection between kernel & user

Think of it as unlocking the “full power” of the CPU safely.

Why Bee Kernel Uses It

Enables kernel & user separation

Allows modern memory management

Supports privilege levels (Ring 0 for kernel, Ring 3 for user)

How We Enter It

Load GDT (Global Descriptor Table) → defines memory segments

Set PE (Protected Enable) bit in CR0 register

Jump to a 32-bit code segment

Initialize kernel stack

Quick Notes

Must set stack before enabling interrupts

Switch to protected mode once at boot

Ensures safe execution environment for kernel & user programs
