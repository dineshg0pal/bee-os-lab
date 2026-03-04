What is Multiboot?

The Multiboot header is a small note in your kernel that tells the bootloader (like GRUB) how to load it safely and provide info like memory layout or modules. Think of it as a “how-to-load-me” card for the bootloader.

Why Bee Kernel Uses It

Safe booting

Memory & module info

Simplifies loading

Example Header
__attribute__((section(".multiboot")))
const uint32_t multiboot_header[] = {
    0x1BADB002, // Magic number
    0x00010003, // Flags
    -(0x1BADB002 + 0x00010003) // Checksum
};

0x1BADB002 → identifies Multiboot

flags → requested info

checksum → ensures header is correct (sum = 0)

Placement

Within first 8 KB of the kernel

Usually at the start of .text section

Quick Points

Required for GRUB to load Bee Kernel

Provides memory & module info

Checksum validates header
