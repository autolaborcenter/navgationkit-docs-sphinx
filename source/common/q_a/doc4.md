## 常见问题 - 其他

<a href="/usedoc/navigationKit2/common/q_a/doc4#nav2">1. 如何编译ROS工作空间？</a>

***

<h5 id="1">1. 如何编译ROS工作空间？</h5>

首次编译，进入catkin_ws/script目录，执行编译脚本（该脚本禁止使用sudo执行）。

`./rebuld`

该脚本执行的是全局编译操作，耗时时间会比较久，第一次编译成功后，如SRC内容有更改，只需catkin_ws目录下，执行以下命令。

`catkin build`
