## How to boot up using qemu?

To boot up using qemu, first you need to create a disk image using the following command:

      `qemu-img create myimage 512`

You can change the size but here we stick to 512 bytes.

Now compile the boot.asm code to boot.bin using:

      `nasm -f bin boot.asm -o boot.bin`

To load our boot.bin generated from our boot.asm on the virtual drive image we use:

      `dd if=boot.bin of=myimage`

then run:

      `qemu-system-x86_64 -drive file=myimage`

If you see Booting from disk then you have succesfully created your first bootloader.

