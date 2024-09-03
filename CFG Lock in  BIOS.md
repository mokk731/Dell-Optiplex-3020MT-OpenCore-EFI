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


--------------------------------------------------

## 进入BIOS后 

开启以下选项：

    VT-x（用于支持Intel虚拟化，也可不开；AMD用户没有此选项）；

    Above 4G decoding（如果AMD用户没有这个选项，则添加npci=0x2000添加到启动参数。二者不能同时启用）；

    Hyper-Threading（Intel超线程技术）；

    Execute Disable Bit（Intel）；

    EHCI/XHCI Hand-off（该项在某些主板上可能和上一个是同一个选项）；

    Boot-OS type: Other（如果你的主板使用Other会导致CSM联动开启，试试选择Windows 8.1/Windows 10 UEFI Mode，或更新主板BIOS版本）；

    X.M.P（内存自动超频，如果有）；

    如果使用Intel核显（不同主板可能名称不同，没有核显不用管）：（1）iGPU/IGFX -> Enable/Auto，开启本项，保存退出BIOS，重启再进入BIOS后才会显示下面选项；（2）Primary Display PEG/PCIE：Auto（仅使用核显就PEG，反之就是PCIE，Auto指的是自适应）；（3）DVMT Total Memory Size：MAX；（4）DVMT Pre-Allocated -> 32M/64M/96M/128M（取决于要用的Framebuffer，高分辨率屏幕不要低于32M）；

    配置SATA为->AHCI；

关闭以下选项：

    Fast Boot；

    Secure boot；

    VT-d（也可以开启，前提是使用OpenCore引导并开启Kernel → DisableIoMapper）；

    CSM（在某些主板上可能没有单独的选项，这种情况选择UEFI模式即可）；

    Intel SGX（笔记本）；

    Intel Platform Trust（笔记本）；

    CFG Lock（MSR 0xE2写保护）；注意：如果BIOS里没有这个选项，OpenCore用户请设置AppleCpuPmCfgLock和Apple；XcpmCfgLock为“Yes”；此项与AMD CPU用户无关；

    Serial Port（串口，有的主板也叫COM Port，macOS安装过程中无故重启、卡死，黑屏等大概率与此项未关闭有关）；

    Parallel Port（并口，此项未关闭可能症状同串口）；

    Re-Size BAR Support（AMD平台称为Smart Access Memory/SAM），如果你有RX6000系显卡则此项可以开启； 

-----------------------------------------------

https://www.youtube.com/watch?v=uS3X13naPcM

解锁BIOS的CFG Lock，完美黑苹果的重要一步，别看步骤多其实特简单   #####



https://apple.sqlsec.com/3-%E5%87%86%E5%A4%87%E5%B7%A5%E4%BD%9C/3-1/

国光的黑苹果安装教程  BIOS设置

CFG Lock

    MSR 0xE2 写保护
    建议关闭，提高黑苹果完美度，很多笔记本没有这些选项，可能需要自己手动去解锁隐藏 BIOS 选项
    如果不关闭的话，config.plist 配置里面设置 AppleXcpmCfgLock 选项为 YES 也是 OK 的 （但是完美度不如关闭 CFG Lock）

VT-d

    I/O 的虚拟化技术，和 VT-x 很容易混淆
    建议关闭，一般搞 PVE 硬件直通才需要开启，正常普通人是用不到硬件直通技术的
    如果不关闭的话，config.plist 配置里面设置 DisableIoMapper 选项为YES 也是 OK 的


OC--Kernel--Quirks--

AppleCpuPmCfgLock

    如果你 BIOS 里面 CFG-Lock 已经关闭那么不需要这个

AppleXcpmCfgLock

    如果你 BIOS 里面 CFG-Lock 已经关闭那么不需要这个

DisableIoMapper

    禁用 XNU（VT-d）中的 IOMapper 支持
    如果 BIOS 里面禁止了 VT-d，那么就不需要勾选了





