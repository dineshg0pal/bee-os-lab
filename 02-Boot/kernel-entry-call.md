🚀 Kernel Entry Point
What is it?

The Kernel Entry Point is the first function that runs after the bootloader passes control to the kernel.
Think of it as the “front door” to your operating system.

Bee Kernel Implementation

Function: kernel_main(uint32_t magic, uint32_t multiboot_addr)

Receives:

magic → validates Multiboot compliance

multiboot_addr → points to boot information

Tasks at entry:

Validate bootloader

Initialize hardware (keyboard, PIT, VGA)

Setup memory (PMM, paging)

Setup interrupts (IDT + ISR)

Load user program

Switch to user mode

Quick Notes

Everything must be initialized before enabling interrupts

Acts as a bridge between bootloader and kernel

Ensures kernel stability and control from the start
