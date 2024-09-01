https://bbs.pcbeta.com/viewthread-1094423-1-1.html

 Mac OS硬件驱动(.kext)安装方法
我当初找到了 T43 用的 Broadcomd 5751 的kext档案 AppleBCM5751Ethernet.kext
我以他为例安装入系统内的步骤如下：
1. 打开终端：
打开终端，执行：

sudo -s

然后键入你的密码，做好切换管理员的动作。
PS. sudo 是一个安全为考虑的执行管理指令的方法，这边不多做介绍。
3. 复制kext 到相应目录：
相应目录是 " /System/Library/Extensions/ " ，
只要把你找到的驱动 .kext 档案复制到 /System/Library/Extensions/ 中，
方法一：直接进入" /System/Library/Extensions/ "目录中，将自己的驱动 .kext 档案复制到里面，中途可能要输入密码；
方法二：假设你的驱动叫AppleBCM5751Ethernet.kext，并放在桌面的，
指令如下：

cp -r ~/Desktop/AppleBCM5751Ethernet.kext /System/Library/Extensions/

注意：请把AppleBCM5751Ethernet.kext换成你自己要安装的.kext驱动名
4. 更改文件权限：
文件权限是UNIX系统中蛮重要的一个观念，在Unix为基础的Mac OS X中也一样，就是要把这些复制到系统内的文件的权限切换成系统（管理员）拥有与使用，指令如下：

sudo chown -R root:wheel /System/Library/Extensions/AppleBCM5751Ethernet.kext
sudo chmod -R 755 /System/Library/Extensions/AppleBCM5751Ethernet.kext

注意：请把AppleBCM5751Ethernet.kext换成你自己要安装的.kext驱动名
5. 清除 kext 的快取：
要清除已经安装并制作快取的kext 快取内容，不然可能下次重启之后系统还是去读取快取，就不会读到新放进去kext 驱动
指令如下：

rm /System/Library/Extensions.kextcache
rm /System/Library/Extensions.mkext
kextcache -k /System/Library/Extensions

6. 系统重启：
硬件驱动后基本上是需要重启才会加载，可以点选右上角的苹果点选重启系统，或是使用指令 reboot 重启，接下来就是祈祷重启后系统一切正常，硬件支持良好啦！
驱动程序其实安装并不难，找不找的到驱动（kext）才是问题。
MAC OS驱动安装与卸载
假设您已经有简单的概念后，我们知道，其实Mac的驱动程序就是 Kernel Extension，
也就是硬件相对应的 .kext 档案，

由于macOS 10.15 锁住了S/L/E的修改权限，因此在修改kext前要使用终端先解锁S/L/E权限
打开终端依次输入

    sudo su
    sudo mount -uw /
    killall Finder 


-------------------------------------------

oc auxiliary tools

https://github.com/ic005k/OCAuxiliaryTools

OCAuxiliaryTools（简称OCAT或ocat） = Config.plist编辑器 + Config.plist数据库


https://heipg.cn/tutorial/applealc-patch.html

使用 AppleALC 驱动黑苹果声卡
下载 AppleALC.kext，把文件放到 /EFI/OC/Kexts/ 目录，然后使用你喜欢的编辑器编辑 config.plist 文件，找到以下位置：
NVRAM → 7C436110-AB2A-4BBB-A880-FE41995C9F82 → boot-args
直接添加启动参数 alcid=1，重启后若没有效果则修改为 alcid=2，以此类推，直到找到适合使用的布局 ID。
