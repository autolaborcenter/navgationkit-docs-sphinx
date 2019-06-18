# 组装和测试

## 电气拓扑

![](./imgs/electrical_topology.png)

## 组装

* Comming soon

## 测试

我们提供了一套工具软件，并将其放置在电脑桌面，你可以用来检测导航套件中各部件能否正常工作

![](./imgs/desktop.png)

1. 激光雷达测试

![](./imgs/lidar_test.png)

2. 惯导测试

![](./imgs/imu_test.png)

3. Kinect测试

![](./imgs/kinect_test.png)

4. 联合测试

## 注意事项

* 尽管锂电池充电接口与工控机、Kinect-Hub电源接口物理外形一致，但他们的电气规格`并不通用`，使用时务必注意，错误的接线方式将会导致设备损坏，甚至危及人身安全

* Kinect-Hub 与工控机之间的连接必须使用USB3.0 接口，否则将无法从工控机读取到Kinect的数据

* 你可以使用我们在电源扩展板上提供的 DC 12V 电源，稳压模块的额定输出为 DC 12V@20A，在外扩设备时请合理计算电源功率