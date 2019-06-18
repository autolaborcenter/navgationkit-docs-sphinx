# 组装与测试

## 电气拓扑

![](./imgs/autolabor_box_v1_electrical_topology.png)

## 组装

* Comming soon

## 测试

我们提供了一套工具软件，并将其放置在电脑桌面，你可以用来检测导航套件中各部件能否正常工作

![](./imgs/autolabor_os_desktop.png)

1. 激光雷达测试

![](./imgs/lidar_test.png)

2. IMU测试

![](./imgs/imu_test.png)

3. Kinect测试

![](./imgs/kinect_test.png)

4. 联合测试

## 常见问题

* “电池充电接口、工控机电源接口、Kinect-Hub电源接口可以互换适配器吗？”

    少年，劝你别有这么大胆的想法！
    
    尽管这三者物理外形一致，但电气规格`并不通用`，使用时务必注意，错误的接线方式将会导致设备损坏，甚至危及人身安全

* “为什么风扇噪音非常大？”

    AMD旗下CPU最大的特点就是~~发热量大~~ 性能强劲，并且工控机内部结构较为紧凑，只有风扇维持在较高转速才保证系统正常工作

* “为什么我看不到Kinect的数据？”

    Kinect-Hub的数据线另一端必须插在工控机 `USB3.0` 接口上，否则将无法从工控机读取到Kinect的数据