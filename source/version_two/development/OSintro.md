# AutolaborOS 

## 简介

AutolaborOS 是由 Autolabor 推出的免费开源机器人操作系统，基于 ubuntu18.04 与 ROS Melodic 开发而成，包含 ROS Melodic 、常用 ROS包（Cartographer、Gmapping、Navigation ···），机器人底盘与传感器驱动包，机器人仿真应用，以及激光SLAM导航、自动巡迹导航应用等。

解决了繁琐的 ROS 环境安装问题，节省时间成本，降低技术壁垒。使用该系统学习ROS、开发机器人、实现自己的算法，做一些有趣的事情。

秉持小而实用的原则，对原生的Ubuntu系统的功能模块进行了精简，在原有的基础上增加了ROS开发中使用到的常见功能包。

既保证了简洁性，又增加了实用性。按需构建，有非常良好的可扩展性。

OS在AP1上已经实现了机器人自主导航（2D/3D SLAM 单目标/多目标）、自动循迹、远程遥控等功能。

Autolabor Pro1 机器人出厂都已预装AutolaborOS。

## 源码说明

注：以下内容基于AutolaborOS 2.2.4

```
catkin_ws
├── script //执行脚本
├── src //源码

catkin_ws/src/driver/
├── car
│   ├── autolabor_canbus_driver //PM1底盘驱动
│   └── autolabor_pro1_driver //AP1底盘驱动
├── depth_camera
│   ├── iai_kinect2-master //kinect V2 相机驱动
│   └── pico_zense_driver //Vzense  DCAM710 相机驱动
├── imu
│   ├── ah100b //ah100b,ah200c 惯导驱动
│   ├── rviz_imu_plugin //rviz 惯导可视化插件，显示惯导图像
│   └── tl740d //tl740d 转角仪驱动
├── joystick
│   └── joystick_drivers // 罗技F710 遥控手柄驱动
├── lidar
│   ├── rplidar_ros //思岚A2 雷达驱动
│   ├── rslidar //速腾RS16 雷达驱动
│   ├── urg_node //北洋Hokuyo UST-10LX 雷达驱动
│   └── wr_fslidar // 砝石FS-D10 雷达驱动
└── location
    └── marvelmind // marvelmind 定位标签驱动

catkin_ws/src/launch/
├── autolabor_navigation_launch //导航launch
│   ├── launch
│   │   ├── real_environment //实车launch
│   │   │   ├── first_generation_base.launch //单雷达版本-传感器驱动
│   │   │   ├── first_generation_mapping.launch //单雷达版本-建图
│   │   │   ├── first_generation_navigation.launch //单雷达版本-导航
│   │   │   ├── second_generation_advanced_base.launch //双雷达版本-传感器驱动(含定位标签)
│   │   │   ├── second_generation_basic_base.launch //双雷达版本-传感器驱动
│   │   │   ├── second_generation_mapping.launch //双雷达版本-建图
│   │   │   ├── second_generation_multigoal_navigation.launch //双雷达版本-多点导航
│   │   │   ├── second_generation_navigation.launch //双雷达版本-导航
│   │   │   ├── second_generation_tracking.launch //双雷达版本-循迹
│   │   │   ├── third_generation_base.launch //多线雷达版本-传感器驱动
│   │   │   ├── third_generation_cartographer_3d.launch //多线雷达版本-建图
│   │   │   └── third_generation_navigation_3d.launch //多线雷达版本-导航
│   │   └── simulated_environment //模拟器launch
│   │       ├── common_stage_simulation.launch //模拟场景地图
│   │       ├── first_generation_base_simulation.launch
│   │       ├── first_generation_mapping_simulation.launch
│   │       ├── first_generation_navigation_simulation.launch
│   │       ├── second_generation_advanced_base_simulation.launch
│   │       ├── second_generation_basic_base_simulation.launch
│   │       ├── second_generation_driver_simulation.launch
│   │       ├── second_generation_mapping_simulation.launch
│   │       ├── second_generation_multicar_following_simulation.launch //多车跟随
│   │       ├── second_generation_multicar_navigation_simulation.launch //多车导航
│   │       ├── second_generation_multigoal_navigation_simulation.launch //多目标导航
│   │       ├── second_generation_navigation_simulation.launch
│   │       └── second_generation_tracking_simulation.launch
│   ├── map //建图保存的地图文件
│   │   ├── map_3d.pbstream //3d slam 地图文件，用于定位，不可修改（保存地图后生成）
│   │   ├── map_3d.pgm //3d slam 地图文件，用于导航，可修改（保存地图后生成）
│   │   ├── map_3d.yaml //map_3d.pgm 的解释文件（保存地图后生成）
│   │   ├── map.pbstream //2d slam 地图文件，用于定位导航，不可修改
│   │   ├── map_simulation.pbstream //模拟器地图文件
│   │   ├── simulation_stage.png //模拟器环境地图
│   │   └── simulation_stage.yaml //simulation_stage.png 的解释文件
│   ├── params //配置文件
│   │   ├── cartographer
│   │   │   ├── first_generation_location.lua //单雷达版本-定位
│   │   │   ├── first_generation_mapping.lua //单雷达版本-建图
│   │   │   ├── map_builder.lua //cartographer 配置文件
│   │   │   ├── map_builder_server.lua //cartographer 配置文件
│   │   │   ├── pose_graph.lua //cartographer 配置文件
│   │   │   ├── second_generation_location.lua //双雷达版本-定位
│   │   │   ├── second_generation_mapping.lua //双雷达版本-建图
│   │   │   ├── second_generation_multicar_location.lua //双雷达版本-多车定位（模拟器）
│   │   │   ├── third_generation_location.lua //多线雷达版本-定位
│   │   │   ├── third_generation_mapping.lua //多线雷达版本-建图
│   │   │   ├── trajectory_builder_2d.lua //cartographer 配置文件
│   │   │   ├── trajectory_builder_3d.lua //cartographer 配置文件
│   │   │   └── trajectory_builder.lua //cartographer 配置文件
│   │   ├── common
│   │   │   ├── back_lidar_config.yaml //后雷达过滤配置文件
│   │   │   └── front_lidar_config.yaml //前雷达过滤配置文件
│   │   └── navigation
│   │       ├── costmap //代价地图配置文件
│   │       │   ├── 3d_global_costmap_params.yaml //3d slam 全局代价地图
│   │       │   ├── 3d_local_costmap_params.yaml //3d slam 局部代价地图
│   │       │   ├── one_laser_global_costmap_params.yaml //单雷达版本-全局代价地图
│   │       │   ├── one_laser_local_costmap_params.yaml //单雷达版本-局部代价地图
│   │       │   ├── two_laser_global_costmap_params_for_tracking.yaml //双雷达版本-循迹-全局代价地图
│   │       │   ├── two_laser_global_costmap_params.yaml //双雷达版本-全局代价地图
│   │       │   └── two_laser_local_costmap_params.yaml //双雷达版本-局部代价地图
│   │       ├── global_planer //全局规划配置文件
│   │       │   ├── global_planner_params.yaml  //用于导航
│   │       │   ├── navfn_params.yaml //用于多车（模拟器）
│   │       │   └── tracking_planner_params.yaml //用于循迹
│   │       ├── local_planer //局部规划配置文件
│   │       │   ├── navigation_teb_local_planner_params.yaml //用于导航
│   │       │   └── tracking_teb_local_planner_params.yaml //用于循迹
│   │       └── move_base //ROS Navigation 配置文件
│   │           ├── navigation_move_base.yaml //用于导航
│   │           └── tracking_move_base.yaml //用于循迹
│   └── rviz //rviz配置文件
│       ├── 3d_mapping.rviz //3d slam-建图
│       ├── 3d_navigation.rviz //3d slam-导航
│       ├── first_generation_create_map.rviz //单雷达版本-建图
│       ├── first_generation_navigation.rviz //单雷达版本-导航
│       ├── second_generation_create_map.rviz //双雷达版本-建图
│       ├── second_generation_multicar_navigation.rviz //双雷达版本-多车导航（模拟器）
│       ├── second_generation_multigoal_navigation.rviz //双雷达版本-多点导航
│       ├── second_generation_navigation.rviz //双雷达版本-导航
│       └── second_generation_tracking.rviz //双雷达版本-循迹
└── autolabor_test_launch //测试
    ├── launch 
    │   ├── car_test.launch //键盘遥控
    │   ├── fslidar_test.launch //砝石FS-D10双雷达测试
    │   ├── imu_test.launch //惯导测试
    │   ├── kinect2_test.launch //kinect V2测试
    │   ├── robot_calibration.launch //AP1标定
    │   └── tag_test.launch //定位标签测试
    └── rviz //rviz配置文件
        ├── car.rviz //键盘遥控
        ├── fslidar.rviz //砝石FS-D10双雷达测试
        ├── robot_calibration.rviz //AP1标定
        └── tag.rviz //定位标签测试


catkin_ws/src/mapping/ //建图源码
├── cartographer //cartographer算法源码
├── cartographer_ros//cartographer算法源码-适配ROS
├── openslam_gmapping //gmapping算法源码
└── slam_gmapping //gmapping-适配ROS


catkin_ws/src/navigation/ //ROS Navigation 源码
├── amcl //粒子滤波定位
├── base_local_planner //局部规划
├── carrot_planner //全局规划
├── clear_costmap_recovery //恢复行为
├── costmap_2d //障碍物地图
├── dwa_local_planner //dwa局部规划
├── fake_localization //OS中未使用
├── global_planner //全局规划
├── location_fusion //定位融合（定位标签+里程计）
├── loop_path_planner //循迹全局规划
├── map_server //地图服务
├── move_base //movebase
├── move_slow_and_clear //恢复行为
├── multi_car_goal //多车-前车向后车发目标（模拟器）
├── nav_core //导航核心接口
├── navfn //全局规划
├── navigation //ROS Navigation元
├── path_rviz_plugin //循迹rviz插件，功能按钮组
├── path_server //用于循迹中录制路线
│   ├── path_data
│   │   ├── default_path.path //循迹中保存的路径数据
├── record_path_planner //循迹全局规划
├── rotate_recovery //恢复行为
├── teb_local_planner //局部规划
└── voxel_grid //用于障碍物地图


catkin_ws/src/simulation/ //模拟器
├── autolabor_description //机器人模型
│   ├── launch
│   │   ├── display_autolabor_mini.launch
│   │   └── display_autolabor_pro1.launch
│   ├── meshes
│   │   ├── autolabor_mini.stl 
│   │   ├── pro1_body_color.dae //AP1模型文件-主体
│   │   └── pro1_wheel_color.dae //AP1模型文件-轮子
│   ├── rviz
│   │   └── urdf.rviz
│   └── urdf
│       ├── autolabor_mini.urdf 
│       ├── first_generation_model.xacro //单雷达版本-机器人描述(类似urdf)
│       ├── second_generation_model.xacro //双雷达版本-机器人描述(类似urdf)
│       └── third_generation_model.xacro //多线雷达版本-机器人描述(类似urdf)
├── autolabor_simulation_base //机器人底盘模拟
├── autolabor_simulation_lidar //雷达模拟
├── autolabor_simulation_location //定位标签模拟
├── autolabor_simulation_object //运动物体模拟
└── autolabor_simulation_stage //场景模拟


catkin_ws/src/tool/
├── autolabor_keyboard_control  //键盘控制（必须要插实体键盘）
├── cartographer_initialpose //cartographer初始化定位
├── image_pipeline //图像处理，OS中未使用
├── joy_to_twist //手柄转速度驱动包
├── navi_multi_goals_pub_rviz_plugin //rviz插件-多点导航
├── rviz_autolabor_calibration //rviz插件-AP1标定
├── rviz_keyboard_twist //rviz插件-键盘控制
└── rviz_navigation_tools  //rviz插件-多车导航工具，切换机器人（模拟器）



script //执行脚本
├── 3d_suit //多线雷达版本
│   ├── create_map_start
│   ├── create_map_stop
│   ├── navigation_start
│   └── navigation_stop
├── box_suit //单雷达版本
│   ├── create_map_start
│   ├── create_map_stop
│   ├── navigation_start
│   └── navigation_stop
├── common
│   ├── add_keyboard_udev //用于键盘控制，加键盘权限
│   └── rebuild //工作空间编译脚本
├── simulation //模拟器
│   ├── create_map_start
│   ├── create_map_stop
│   ├── navigation_start
│   ├── navigation_stop
│   ├── tracking_start
│   └── tracking_stop
├── test //测试
│   ├── car_test
│   ├── fslidar_test
│   ├── imu_test
│   ├── kinect2_test
│   ├── pico_test
│   ├── robot_calibration
│   ├── rplidar_test
│   ├── rslidar_test
│   └── tag_test
└── track_suit //双雷达版本
    ├── create_map_start
    ├── create_map_stop
    ├── navigation_start
    ├── navigation_stop
    ├── tracking_start //开始循迹
    └── tracking_stop //停止循迹
```