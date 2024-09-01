https://heipg.cn/tutorial/macserial-and-iservice-opencore.html

OpenCore生成三码，修复苹果服务无法使用


iMac14,4 : iMac (21.5-inch, Mid 2014)；适合四代酷睿HD4400/4600核显无独显使用。

iMac14,3   i5-4570S@2.9G, 4C4T ,HD Graphics 4600

iMac 15,1,  带独立显卡


选定了机型后，下一步就是三码，具体是哪些？请看：

    MLB：Main Logic Board serial number，主逻辑板序列号
    SystemSerialNumber：正如其名，系统序列号
    SystemUUID：System Universally Unique Identifier，系统通用唯一识别码

除了上面这三个之外，和苹果服务相关的还有 ROM 值，黑苹果一般用网卡 MAC（Media Access Control Address）地址代替，除此之外还有另一种白苹果 MAC 地址混搭的方法，下文会一起介绍。

-----------------------------------------------------------------------


我们常说的“修改 OC 配置文件”指的就是修改 /EFI/OC/ 目录下的 config.plist 文件，这是 OpenCore 的核心配置文件。考虑到目前已经有各式各类的工具可配置 OpenCore，这里提供多种工具和方法，选择其中之一即可：

OpenCore Configurator：简称 OCC，和开发 Clover 配置工具的是同一个团队，优点是拥有逻辑清晰的图形界面，操作比较直观；缺点是只有 macOS 版本，并且偶尔会出现污染配置文件的情况，使用前注意备份；

OCAuxiliaryTools：OpenCore 配置工具中的后起之秀，优点是拥有跨平台客户端，支持 Windows、macOS 和 Linux，拥有图形界面，操作比较直观；缺点是功能排版上稍显凌乱，和 OCC 一样偶尔会出现污染配置文件的情况，使用前注意备份；

ProperTree：使用 Python 编写的跨平台 Plist 编辑工具，优点是可跨平台，支持 Windows、macOS 和 Linux（Python），通常情况下不会污染配置文件；缺点是虽然拥有图形界面，但却是一个树状的编辑器，和前两者不是同一个概念，因此操作上没有前二者方便；

Visual Studio Code：严格来说这是一个代码编辑器，同类型的还有 Sublime Text，UltraEdit 等，其优点是自由度较高，不会污染配置文件；缺点是没有代码基础知识没法使用，较高的自由度也带来了犯更多错的可能；

-----------------------------------------------------------------------

https://geekdaxue.co/read/hejianzhao@zgnsc5/uu5xhg

GenSMBIOS 生成SMBIOS
在最后加上数字5，可以一次显示5套SMBIOS，注意留空格：

生成后，请到这里验证，Apple Check https://checkcoverage.apple.com/

序列号：Serial项
提示“无效的序列号”或“未验证购买日期”才可以使用

这个网站可以验证Config.plist，对我们非常有用https://opencore.slowgeek.com/
