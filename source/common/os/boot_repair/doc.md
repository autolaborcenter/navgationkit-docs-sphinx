# 引导修复

当你的设备显示类似这样的画面，并且无法进入系统时，这表明是操作系统的引导出了故障，本文将帮助你修复系统引导。

  ![](imgs/boot_repair_grub2.jpg)

## 开始

* 进入Live版AutolaborOS[参考此处](../live/doc.md)

* 通过Wi-Fi或网线将Live版AutolaborOS接入互联网

* 运行如下命令

  1.添加软件源

  ```
  sudo add-apt-repository ppa:yannubuntu/boot-repair
  ```

  2.安装`boot-repair`
  ```
  sudo apt-get install -y boot-repair
  ```

  3.启动`boot-repair`
  ```
  boot-repair
  ```

* 选择`Reconmmended repair`

  ![](imgs/boot_repair_bootup.jpg)

* 引导修复完成后，请弹出U盘并重启

## 常见问题



