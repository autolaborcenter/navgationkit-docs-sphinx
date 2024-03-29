# 安装操作系统

如果你的操作系统运行异常、或准备清空文稿资料，本文将帮助你如何安装出厂版本的操作系统。

## 准备

* Autolabor OS 镜像盘 * 1

* 可能需要：

  > AutolaborOS 镜像[下载](http://www.autolabor.com.cn/download)

  > 镜像烧录指南[参考此处](/usedoc/navigationKit2/common/os/flash/doc)

## 开始

  > 注意核对机型

![](imgs/install_os_complex.gif)

## 常见问题

* “启动选项中找不到教程中提到的设备？”

  由于生产批次不同，您看到的启动优盘名称可能有差异，一般会是以下几种：  “Generic Mass-Storage 1.11” 、 “HP v285w 1100” 、 “USB DISK 2.0 PMAP”

* “我可以把 Autolabor OS 安装到其他硬件平台吗？”

  原则上，Autolabor OS 兼容市面所有 X86/AMD64 架构硬件平台，但我们无法保证其可用性。

  如果你富有挑战精神，我们也欢迎你尝试把 Autolabor OS 安装在任何 X86/AMD64 设备上，更欢迎给我们提出兼容性报告。

  为获得最佳使用体验，推荐使用 Autolabor PC 来搭载 Autolabor OS。

* “开机启动时是否可以选择UEFI启动？”

  可以，但此部分属于高级用户功能，你要确保自己了解每一步都在做什么，并建议提前备份个人数据。

* “安装 OS 时选择全自动安装，还是自定义安装？”

  建议使用空硬盘进行**全自动**安装，自定义安装需要安装时设置分区，至少三个分区，一个swap，一个efi，还有一个主分区。每个分区的格式也要选对，这个操作错误容易洗掉硬盘。

  自定义安装硬盘设置错误，安装时会产生报错，如无法安装 GRUB 等。
