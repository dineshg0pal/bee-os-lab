#💿 GRUB Bootable ISO
##What is it?

A GRUB Bootable ISO is a ready-to-run disk image of your kernel that GRUB can load.
Think of it as “packaging your kernel so the PC can start it”.

#Bee Kernel Implementation

Use GRUB as the bootloader

##Steps to make ISO:

Compile your kernel (kernel.bin)

Create a folder structure:

iso/
  └── boot/
      ├── grub/
      │   └── grub.cfg
      └── kernel.bin

grub.cfg tells GRUB which kernel to load:

menuentry "Bee Kernel" {
    multiboot /boot/kernel.bin
    boot
}

#Generate ISO:

grub-mkrescue -o bee.iso iso/
Quick Notes

ISO can be run in QEMU, VirtualBox, or burned to USB

GRUB handles multiboot headers and loading the kernel

Makes testing easier and kernel is portable
