## Important BIOS settings

In case of 3020 MT and 3020 SFF computers

1, Download [modGRUBShell](https://github.com/datasone/grub-mod-setup_var/releases) and place it in the EFI/OC/Tools folder. Add it to the Misc → Tools section of config.plist.

2, Boot into OpenCore and select the modGRUBShell option.

3, Enter the following values:

   Disable CFG Lock:

    setup_var 0xD9E 0x0
    
  Set DVMT pre-alloc to 64MB:

    setup_var 0x263 0x2
  Enable EHCI hand-off:

    setup_var 0x2 0x1
    setup_var 0x144 0x1
    setup_var 0x15A 0x2
    setup_var 0x146 0x0
    setup_var 0x147 0x0
4. Reboot the system when done.


-------------------------------------------

本项目已在EFI-OC 中关闭 CFG Lock ，不用改BIOS.
