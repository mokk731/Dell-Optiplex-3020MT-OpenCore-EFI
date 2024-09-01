https://blog.daliansky.net/macOS-Catalina-10.15.7-19H2-Release-version-with-Clover-5122-original-image-Double-EFI-Version-UEFI-and-MBR.html

【黑果小兵】macOS Catalina 10.15.7 19H15 正式版 with Clover 5126原版镜像[双EFI版] [UEFI and MBR]

https://blog.daliansky.net/WeChat-First-macOS-Catalina-10.15.7-19H15-official-version-Clover-5126-OC-WEPE-supports-both-INTEL-and-AMD-original-images.html

【微信首发】macOS Catalina 10.15.7 19H15 正式版 Clover 5126/OC/PE三分区支持Intel及AMD双平台原版镜像

10.15.7 19H2  MD5

16GB   b44de9c1aa8aea1c7414b0d14f187b55

32GB   f54c4c5c0bf930643469b7f064078fda


我下载的BT文件:

    macOS Catalina 10.15.7 19H2.dmg               7.7GB            ####################

    magnet:?xt=urn:btih:8FE3D5E14715C6F2C60B6433AF230A281CFDF8DD

    MD5:  5f15506a22a11a0fe17e3dae463fceb8   ????




https://www.sysgeek.cn/macos-version-history/

macOS 版本历史回顾：从 2001 到 2024，功能、代号和发布时间


2020 年 11 月 10 日发布的 Big Sur 标志着 macOS 发展史上的一个重要里程碑。此版本带来了重大的设计变革，是第一个支持搭载 Apple Silicon 芯片的 Mac 系统，同时也是首个允许 iOS 应用程序在 Mac 上原生运行（称为通用应用程序）的 macOS 版本。

macOS BigSur 11.7.10(20G1427)with OpenCore 0.9.6以及Clover r5155 and FirPE

    获取链接1：https://pan.quark.cn/s/deaf156606ff 

macOS Big Sur 11.6.8 (20G730) [MAS].dmg

    magnet:?xt=urn:btih:04BC3ABC6D8D659323B6286A5FF1FE1495AC6B76

Install macOS Big Sur 11.5.1 (20G80).dmg

    magnet:?xt=urn:btih:3C5772730865188F153BCCF0550E0780F19C9E76

------------------------------------------------------

https://blog.daliansky.net/Common-problems-and-solutions-in-macOS-Catalina-10.15-installation.html

macOS Catalina 10.15安装中常见的问题及解决方法
Apple已经删除了我们必须避免APFS转换的选项，常规的方法已经无法避免安装过程中自动将分区转换为APFS格式，包括在硬盘上安装以及SSD上面安装。


https://blog.daliansky.net/Lenovo-Tianyi-510s-Mini-and-macOS-BigSur-Installation-Tutorial.html

天逸510s Mini兼macOS BigSur安装教程


https://blog.daliansky.net/Common-problems-and-solutions-in-macOS-BigSur-11.0-installation.html

macOS BigSur 11.0安装中常见的问题及解决方法



https://blog.daliansky.net/Common-problems-and-solutions-in-macOS-Catalina-10.15-installation.html

macOS Catalina 10.15安装中常见的问题及解决方法

------------------------------------------------------

## Downloading macOS

https://dortania.github.io/OpenCore-Install-Guide/installer-guide/windows-install.html

https://github.com/acidanthera/OpenCorePkg/releases

To grab legacy installers is super easy, first grab a copy of OpenCorePkg (opens new window) and head to /Utilities/macrecovery/. Next, click next to the current folder path and type cmd to open a Command Prompt in the current directory:

Now run one of the following depending on what version of macOS you want(Note these scripts rely on Python 3 (opens new window) support, please install if you haven't already):

create a new simple volume. Make sure it is FAT32 and at least a gigabyte or two big. Name it "EFI".
Next, go to the root of this USB drive and create a folder called com.apple.recovery.boot. Then move the downloaded BaseSystem or RecoveryImage files. Please ensure you copy over both the .dmg and .chunklist files to this folder

    # Mojave (10.14)
    py macrecovery.py -b Mac-7BA5B2DFE22DDD8C -m 00000000000KXPG00 download

    # Catalina (10.15)
    py macrecovery.py -b Mac-00BE6ED71E35EB86 -m 00000000000000000 download

    # Big Sur (11)
    py macrecovery.py -b Mac-42FD25EABCABB274 -m 00000000000000000 download

    # Monterey (12)
    py macrecovery.py -b Mac-FFE5EF870D7BA81A -m 00000000000000000 download
