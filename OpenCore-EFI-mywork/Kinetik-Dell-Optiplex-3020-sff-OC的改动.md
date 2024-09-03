
不能正常引导，但将 BIOS的CFG Lock 解锁， 就可以正常引导！！ 

网卡，声卡正常。声卡有内置+耳机。但核显共享显存才7MB.




1, 缺少 ResetNvramEntry.efi

UEFI --Drives

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
    
4, 核显共享显存大小修改

DP---PciRoot(0x0)/Pci(0x2,0x0)

    AAPL,ig-platform-id      	Data 	   0300220D

    device-id         	        Data 	   12040000

    framebuffer-patch-enable 	Data   	  01000000

    framebuffer-stolenmem 	    Data 	  00003001

    framebuffer-fbmem  	       Data 	  00009000

    framebuffer-unifiedmem     Data       00000080 

    
