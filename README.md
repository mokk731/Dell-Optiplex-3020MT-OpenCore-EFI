# Dell-Optiplex-3020MT-OpenCore-EFI
Dell-Optiplex-3020MT-OpenCore-EFI, Hackintosh



https://github.com/tbwcjw/Dell-Optiplex-3020M-EFI         #####

This repository contains EFI files for my Dell Optiplex 3020M, tested and confirmed to work with macOS Catalina 10.15.7.

可以正常引导！！！但网卡，声卡不正常。 加入网卡驱动，改声卡驱动，就能正常使用。共享显存1.5GB


https://github.com/Kinetik/Dell-Optiplex-3020-sff-OC   #####

This repository contains a fully working (with standard hardware) EFI package with you can use to install all macOS versions up to Big Sur.

不能正常引导，但将 BIOS的CFG Lock 解锁， 就可以正常引导！！ 网卡，声卡正常。声卡有内置+耳机。但共享显存才7MB.

https://github.com/varszegimarcell/Optiplex-3020-Hackintosh-OpenCore         #####

This repository contains a guide on how to install macOS on the Dell Optiplex 3020, with the neccesary files.iMac15,1

不能正常引导，但将 BIOS的CFG Lock 解锁，也不行。打了三码，才能进入选择菜单，但进不了正常引导原来装好的MAC OS，，大神设置了好多关卡，我就不玩了。

https://github.com/daliansky/Hackintosh

-------------------------------------------------------------------

## 我的硬件表：

CPU  :  E3-1225 V3

主板 ：  Dell optiplex 3020mt 主板    H81  

内存  ： DDR3 1333 2G*2

显卡 ：  核显HD P4600

声卡 ：  Realtek ALC280 

网卡 ：  RTL8111/RTL8168

SSD  ：  32G sata ssd

bios ：  AMI uEFI

Networking : Generic Intel PCIE NIC (7265) ----tbwcjw

iMac14,3 i5-4570S@2.9G, 4C4T ,HD Graphics 4600

intel 4代 Haswell 核心，Mac最高只支持到 macOS BigSur 11 .

不要升级Big Sur系统,Big Sur系统对M1开始适配，对intel不友好.

Catalina够用了。

-------------------------------------------------------------------

1, 能正常引导安装 macOS Catalina 10.15.7

2，Dell optiplex 3020mt 主板 BOIS的选项很少， 

        BIOS没有选项。三个重要设置：

       1，  Disable CFG Lock:

        2， Set DVMT pre-alloc to 64MB

        3， Enable EHCI hand-off
    
       可发在 EFI-OC 中关闭。
       CFG Lock
       config.plist 配置里面设置Kernel--Quirks--AppleXcpmCfgLock 选项为 YES
       VT-d
       config.plist 配置里面设置Kernel--Quirks--DisableIoMapper 选项为YES

3, macOS视频输出，VGA接口不支持，只能用DP口，可用DP口转HDMI口转换器，转成HDMI信号。



-------------------------------------------------------------------

本项目在 https://github.com/tbwcjw/Dell-Optiplex-3020M-EFI  基础上，优化改动。感谢tbwcjw的无私分享。


v1.0.1项目

    1, 增加了RTL8111网卡驱动，  

    2, 改动Realtek ALC280 声卡驱动

    3,  tbwcjw 原EFI支持 Intel PCIE NIC 7265 ，给与保留。

    4,  MLB，SystemSerialNumber，SystemUUID
      三码空白，要用OCAuxiliaryTools 填写自己的。
      








