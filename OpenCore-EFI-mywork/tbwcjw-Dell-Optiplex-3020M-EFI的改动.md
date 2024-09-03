可以正常引导！！！但网卡，声卡不正常。 

加入网卡驱动，改声卡驱动，就能正常使用。共享显存1.5GB


1, 加入RTL8111网卡驱动

    Kernel--Add---RealtekRTL8111.kext

    或进入Mac OS 后，先解锁S/L/E权限.
    
    cp -r ~/Desktop/RealtekRTL8111.kext /System/Library/Extensions/

2, 改声卡驱动

   Realtek ALC280 alcid=3，4，11，13，15，16，17,18,21
  
       NVRAM → 7C436110-AB2A-4BBB-A880-FE41995C9F82 → boot-args   alcid=11  （临时用）

       或.DP--PciRoot---layout-id  11000000    (正式用)

   



