# GRUB Bootable ISO 🚀

A **bootable ISO** lets your Bee Kernel run on real hardware or in emulators like QEMU.  

**Steps in short:**  
1. Install GRUB tools (`grub-pc-bin`, `xorriso`).  
2. Create an `iso/boot` folder with your kernel binary and `grub.cfg`.  
3. Write a simple `grub.cfg` with a menu entry pointing to your kernel.  
4. Use `xorriso` to generate the bootable ISO.  
5. Test with QEMU or on a USB.  

> GRUB loads the kernel into memory and passes control to it. Multiboot format is required for compatibility.
