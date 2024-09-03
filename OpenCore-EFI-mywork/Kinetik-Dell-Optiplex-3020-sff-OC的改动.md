
不能正常引导，但将 BIOS的CFG Lock 解锁， 就可以正常引导！！ 

网卡，声卡正常。声卡有内置+耳机。但共享显存才7MB.




1, UEFI --Drives

    ResetNvramEntry.efi   加载

    Enabled 开

    LoadEarly  关


2, UIScale is set under both NVRAM and UEFI---wrong

    UEFI --Output--- UIScale 1
    
    NVRAM --Add--4D1EDE05-38C7-4A6A-9CC6-4BCCA8B38C14----  UIScale   del

3, 解锁BIOS的CFG Lock

    Kernel--Quirks---AppleXcpmCfgLock 开

    或：Boot into OpenCore and select the modGRUBShell option.

    setup_var 0xD9E 0x00

