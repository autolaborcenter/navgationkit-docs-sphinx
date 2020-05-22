# 定位路由、标签故障排查流程

## 1.设备插上电脑后，电脑无法识别

定位路由或定位标签（必须要打开电源），插上电脑会自动安装驱动，在设备管理器-端口中，能看到对应设备。

如插上后显示不能识别，端口下无设备，请检查数据线是否插紧，确定插紧后仍未识别：

尝试手动安装驱动，https://marvelmind.com/pics/stm32_vcp.zip

如手动安装后仍未能识别，请取2个设备，标签/路由，2根数据线，进行交叉测试。

判断是数据线，还是设备故障。


## 2.Dashboard 软件打开故障

Dashboard 软件由硬件方提供，目前对于各个系统的兼容性有差异，推荐使用 WIN7/XP环境。

如在Win10 系统下遇到以下故障，请点击Abort，再次打开软件，多次Abort尝试后会正常。

>Access violation.
>Press OK to ignore and risk data corruption.
>Press Abort to kill the program.


## 3.路由连接电脑，Dashboard 软件打开后，无法找到路由 Not found modem connection to computer through USB.

请检查在设备管理器-端口中，是否有设备。

无如设备，请参见第1条。



