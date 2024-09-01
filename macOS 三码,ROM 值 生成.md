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

https://geekdaxue.co/read/hejianzhao@zgnsc5/uu5xhg
GenSMBIOS 生成SMBIOS
在最后加上数字5，可以一次显示5套SMBIOS，注意留空格：

生成后，请到这里验证，Apple Check https://checkcoverage.apple.com/
序列号：Serial项
提示“无效的序列号”或“未验证购买日期”才可以使用

这个网站可以验证Config.plist，对我们非常有用https://opencore.slowgeek.com/
