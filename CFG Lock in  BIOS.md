## Important BIOS settings

Download [modGRUBShell](https://github.com/datasone/grub-mod-setup_var/releases) and place it in the EFI/OC/Tools folder. Add it to the Misc → Tools section of config.plist.

Boot into OpenCore and select the modGRUBShell option.

Enter the following values:

Disable CFG Lock:

setup_var 0xD9F 0x0
Set DVMT pre-alloc to 64MB:

setup_var 0x263 0x2
Enable EHCI hand-off:

setup_var 0x2 0x1
setup_var 0x144 0x1
setup_var 0x15A 0x2
setup_var 0x146 0x0
setup_var 0x147 0x0
Reboot the system when done.
