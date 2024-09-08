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

    # High Sierra (10.13)
    py macrecovery.py -b Mac-7BA5B2D9E42DDD94 -m 00000000000J80300 download
    py macrecovery.py -b Mac-BE088AF8C5EB4FA2 -m 00000000000J80300 download

    # Mojave (10.14)   #####
    py macrecovery.py -b Mac-7BA5B2DFE22DDD8C -m 00000000000KXPG00 download

    # Catalina (10.15)
    py macrecovery.py -b Mac-00BE6ED71E35EB86 -m 00000000000000000 download
    py macrecovery.py -b Mac-CFF7D910A743CAAF -m 00000000000PHCD00 download

    # Big Sur (11)
    py macrecovery.py -b Mac-2BD1B31983FE1663 -m 00000000000000000 download

    # Monterey (12)
    py macrecovery.py -b Mac-E43C1C25D4880AD6 -m 00000000000000000 download
    

    # Ventura (13)
    py macrecovery.py -b Mac-B4831CEBD52A0C4C -m 00000000000000000 download
   
-------------------------------------------------------------------------------------------

https://support.apple.com/zh-cn/102662

如何下载和安装 macOS


    https://apps.apple.com/cn/app/macos-mojave/id1398502828?ls=1&mt=12
    macOS Mojave

    https://apps.apple.com/cn/app/macos-catalina/id1466841314?mt=12
    macOS Catalina

    https://apps.apple.com/cn/app/macos-monterey/id1576738294?mt=12
    macOS Monterey

    -Mojave
    InstallESD.dmg
    5.16 GB

    -Catalina
    InstallESD.dmg
    7.20 GB

    
https://support.apple.com/zh-cn/101578

创建可引导的 macOS 安装器

https://www.cnblogs.com/sysin/p/18241861

 如何创建可引导的 macOS Sequoia 15 安装介质

https://macoshome.com/course/7096.html

使用终端命令制作macOS安装U盘(可引导启动的macOS系统安装盘) 


支持10.13以上版本的Mac请下载：macOS Big Sur、macOS Catalina、macOS Mojave 或 macOS High Sierra 
所有从App Store商店下载的镜像都会作为名为“安装 macOS [版本名称]”的 App 下载到你的“应用程序”文件夹里面。如果安装器在下载后打开，直接点击退出不要继续安装。

确保你下载的.app安装镜像都在应用程序文件夹内！非常重要！在“终端”中键入或粘贴以下命令之一。其中“MyVolume”是你U盘或者移动硬盘的名称。如果不是这个名称，请将这些命令中的 MyVolume 替换为你要制作的U盘或者移动硬盘的名称。注意：整个U盘或者移动硬盘都会被格式化用来制作安装盘，有东西要备份走。

    sudo /Applications/Install\ macOS\ Catalina.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume


键入命令后：

    按下 Return 键以运行这个命令。
    出现Password提示时，输入你的Mac管理员密码(开机密码)，然后再次按下 Return 键。这个位置输入密码时，“终端”不会显示任何字符。
    出现提示时，请键入 Y 以确认你要抹掉宗卷，然后按下 Return 键运行。在抹掉宗卷的过程中，“终端”会显示进度。
    宗卷被抹掉后，你可能会看到一条提醒，提示“终端”要访问可移除宗卷上的文件。点按“好”以允许继续拷贝。 
    当“终端”显示操作已完成时，你会在桌面看到一个对应镜像版本的名称盘，例如Install macOS Big Sur，就可以退出“终端”并推出安装U盘了。

启动安装U盘

    1.把要重装系统的电脑关机，把制作好的macOS安装u盘插上Mac电脑，

    2.然后按下电源键开机，接着马上按住Option键三秒以上再松开；

    3.等出现选择界面之后，选择你制作好的安装U盘系统，如果是Big sur 系统，就会显示一个Big sur 圆形图标，选择它按回车键（Return键），开始从安装U盘引导启动了。



