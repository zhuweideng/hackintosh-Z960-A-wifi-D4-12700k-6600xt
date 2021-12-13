# 黑苹果 OpenCore配置 for ASUS ROG z690-A 12700K 

##
CpuTopologySync.kext 及相关补丁必须禁用。
新编译的OpenCore.efi  0.7.7
替换它并使 ProvideCurrentCpuInfo=true
SMCProcessor.kext也按预期工作
CPUFriendDataProvider.kext也需要添加

#### EFI说明：
1】本EFI基于以下硬件环境，如果你的硬件环境不一致，重点修改USB定制或其它硬件驱动。
主板：ROG STRIX Z690-A GAMING WIFI D4吹雪
CPU：12700K盒装
显卡：华硕6600XT
内存：64G 3200 DDR4
显示器：AOC 卢瓦尔4K
系统环境： macOS Monterey 12.1beta
仿冒机型：MacPro7,1

2】有线网卡为Intel(R) Ethernet Controller I225-V
3】无线网卡为此主板的无线网卡，已经正常驱动
4】此主板集成蓝牙目前不能正常稳定使用，你可以自己配置蓝牙模块。
5】显卡若不一致，如果不能驱动，请加载WG（默认未加载）
6】USB可以根据自己的主板重新定制
7】此主板声卡默认已经驱动，显示为Realtek USB2.0 Audio
8】ACPI中的补丁，可以自己测试，是否需要，不需要禁用
9】处理器型号可以在NVRAM配置项中修改
10】其它根据自己的硬件环境修改


## 更新日志
- 21年12月12日 opencore 升级到 0.7.7 正式版 

## 硬件配置
- 主板：华硕 PRIME
- CPU：i7-12700k @ 3.6GHz
- 显卡：华硕
- 内存：
- 硬盘：

## BIOS设置（重要）
#### disable
- Fast Boot(快速启动)
- CFG Lock(CFG 锁)
- VT-d
- CSM(兼容性支持模块)
#### enable
- VT-x 
- Above 4G decoding(大于 4G 地址空间解码)
- Hyper Threading(处理器超线程)
- Execute Disable Bit(执行禁止位)
- EHCI/XHCI Hand-off(接手 EHCI/XHCI 控制)
- OS type: other types(操作系统类型: 其他)

## 其他
- [OpenCore 实时编译地址](https://github.com/williambj1/OpenCore-Factory/releases)
- [Kexts 下载地址](https://gitee.com/evu/Easy-Kexts)
- [xjn 大佬的博客](https://blog.xjn819.com/?p=543)
- [主题资源文件 OcBinaryData](https://github.com/acidanthera/OcBinaryData)
- [文档](https://dortania.github.io/OpenCore-Post-Install/)
- [文档2](https://github.com/daliansky/OC-little)
- [ACPI定制USB端口](https://github.com/daliansky/OC-little/blob/master/15-ACPI%E5%AE%9A%E5%88%B6USB%E7%AB%AF%E5%8F%A3/README.md)
- [Intel无线网卡](
https://github.com/OpenIntelWireless/itlwm/releases)
- [参考地址远景地址](https://bbs.pcbeta.com/viewthread-1915402-1-1.html)

## Mac OS 下载地址
-  [macOS Big Sur](https://apps.apple.com/cn/app/macos-big-sur/id1526878132?ls=1&mt=12)
-  [macOS Catalina](https://apps.apple.com/cn/app/macos-catalina/id1466841314?ls=1&mt=12)
-  [macOS Mojave](https://apps.apple.com/cn/app/macos-mojave/id1398502828?ls=1&mt=12)
-  [macOS High Sierra](https://apps.apple.com/cn/app/macos-high-sierra/id1246284741?ls=1&mt=12)
-  [macOS Monterey](https://apps.apple.com/cn/app/macos-monterey/id1576738294?mt=12)

## 制作启动盘
> sudo /Applications/Install\ macOS\ Big\ Sur.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolumeName