## Important BIOS settings

In case of 3020 MT and 3020 SFF computers

1, Download [modGRUBShell](https://github.com/datasone/grub-mod-setup_var/releases) and place it in the EFI/OC/Tools folder. Add it to the Misc → Tools section of config.plist.

2, Boot into OpenCore and select the modGRUBShell option.

3, Enter the following values:

   Disable CFG Lock:

    setup_var 0xD9E 0x0
    
    实际：原0x01，改为0x00
    
  Set DVMT pre-alloc to 64MB:

    setup_var 0x263 0x2

    实际：原0x01，改为0x02
    
  Enable EHCI hand-off:

    setup_var 0x2 0x1
    setup_var 0x144 0x1
    setup_var 0x15A 0x2
    setup_var 0x146 0x0
    setup_var 0x147 0x0

    实际：太复杂，没改，只在config.plist 配置里面设置Kernel--Quirks--XhciPortLimit
    
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

完整的 Quiks 怪癖，，，Kernel--Quirks

因为各个平台的版本不太一样，在详细说明之前写来一个 OC 0.7.3 完整的 Quiks 怪癖 说明，这样心里大家设置的时候心里一般就有个底了。

    AppleCpuPmCfgLock
        如果你 BIOS 里面 CFG-Lock 已经关闭那么不需要这个
    AppleXcpmCfgLock
        如果你 BIOS 里面 CFG-Lock 已经关闭那么不需要这个
    AppleXcpmExtraMsrs
        对没有本机 XCPM 支持的某些 CPU 禁用多个关键 MSR 访问
        主要是在无原生电源管理的 CPU上 使用
        一般是Haswell-E，Broadwell-E，Skylake-X这三种 CPU 才勾选使用
    AppleXcpmForceBoost
        强制在 XCPM 模式下实现最大性能
        强制拉高睿频 建议在长期高负载的专业设备上使用
        某些 Xeon 系列的处理器开启这个选项会受益
    CustomSMBIOSGuid
        为 UpdatesBiosModeCustom 自定义模式执行 GUID 修补
        戴尔笔记本电脑通常要勾选这个
        如果你的笔记本无法正常显示序列号的话，也可以勾选试试看
    DisableIoMapper
        禁用 XNU（VT-d）中的 IOMapper 支持
        如果 BIOS 里面禁止了 VT-d，那么就不需要勾选了
    DisableLinkeditJettison
        此选项允许 Lilu.kext 和可能的其他 kext 在 macOS Big Sur 中以最佳性能级别运行
        而不需要在启动项中添加 keepsyms=1，相当于替代掉了他
    DisableRtcChecksum
        禁用在 AppleRTC 中写入主校验
    ExtendBTFeatureFlags
        将 FeatureFlags 设置为0x0F，以实现蓝牙的全部功能
    ForceSecureBootScheme
        强制 x86 方案用于 IMG4 验证
        当使用不同于 x86 legacy 的 SecureBootModel 时，虚拟机上需要此选项
    IncreasePciBarSize
        将 IOPCIFamily 中的 32 位 PCI Bar 大小从 1GBs 增加到 4GBs
        需要此选项表示固件配置错误或有缺陷，所以一般也不使用
    LapicKernelPanic
        禁用由 AP 核心 lapic 中断造成的内核崩溃
        用于惠普笔记本的内核奔溃，如果没有奔溃的话就不建议勾选了
    LegacyCommpage
        将默认的 64 位 commpage bcopy 实现替换为不需要 SSE3 的实现
        这对于传统的老平台非常有用 10.4-10.6
        新平台基本上不勾选使用
    PanicNoKextDump
        在发生内核崩溃时阻止输出 Kext 列表, 提供可供排错参考的崩溃日志
        排错时的时候建议开启
    PowerTimeoutKernelPanic
        修复 macOS Catalina 中由于设备电源状态变化超时而导致的内核崩溃
        当遇到睡眠不能唤醒，只有重启后才能唤醒的情况下勾选
        台式机一般不勾选
    ProvideCurrentCpuInfo
        向内核提供当前 CPU 信息
    SetApfsTrimTimeout
        10.14 之前的版本不需要设置
        主要针对 SATA SSD，根据不同的主控，设置不同的延迟
    ThirdPartyDrives
        为 SSD 启用 TRIM 指令，可能会改善休眠情况
        NVMe SSD 会自动被 macOS 加载因此不需要
        SATA SSD 可以在终端执行 sudo trimforce enable 开启，效果一样
    XhciPortLimit
        解除 15 个端口限制，确认 USB 端口完美定制的可以不勾选




