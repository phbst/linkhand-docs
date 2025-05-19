# LinkerHand灵巧手ROS2 SDK

## 概述

LinkerHand灵巧手ROS SDK 是灵心巧手(北京)科技有限公司开发，用于L7、O7、L10、O10等LinkerHand灵巧手的驱动软件和功能示例源码。可用于真机与仿真器使用。  
LinkerHandROS2 SDK当前支持Ubuntu22.04 ROS humble Python3.10 及以上环境  
SDK 下载地址：[https://github.com/linkerbotai/linker\_hand\_ros2\_sdk](https://github.com/linkerbotai/linker_hand_ros2_sdk)

## 安装

  确保当前系统环境为Ubuntu20.04 ROS 2 Foxy Python3.8.20 及以上

- 下载

bash 复制代码

```bash
  $ mkdir -p linker_hand_ros2_sdk/src
  $ cd linker_hand_ros2_sdk/src
  $ git clone https://github.com/linkerbotai/linker_hand_ros2_sdk.git
```

- 编译

bash 复制代码

```bash
  $ cd linker_hand_ros2_sdk/src/
  $ pip install -r requirements.txt
```

## 使用

   **使用前请先将setting.yaml 配置文件根据实际需求进行相应修改该.**  
   **使用前请先将load\_write\_yaml.py文件第28行的yaml\_path ="" 改为config目录的绝对路径.**

- 启动SDK    将linker\_hand灵巧手的USB转CAN设备插入Ubuntu设备上

bash 复制代码

```bash
  # 开启CAN端口
  $ sudo /usr/sbin/ip link set can0 up type can bitrate 1000000 #USB转CAN设备蓝色灯常亮状态
  $ cd linker_hand_ros2_sdk/
  $ colcon build --symlink-install
  $ source ./install/setup.bash
  $ ros2 run linker_hand_ros2_sdk linker_hand_sdk
```

- 启动状态波形图(带有压力传感器的LinkerHand)

bash 复制代码

```bash
# 启动ROS2 SDK后新开终端
$ cd linker_hand_ros2_sdk/
$ source ./install/setup.bash
$ ros2 run graphic_display graphic_display
```

## 版本更新

- > ### release\_1.0.2
  
  - 1、支持L10/O10版本灵巧手
  - 2、支持GUI控制L10/O10版本灵巧手
  - 3、增加支持压力传感器的LinkerHand波形图显示传感器状态
- > ### release\_1.0.1
  
  - 1、支持L7/O7版本灵巧手
  - 2、支持GUI控制L7/O7版本灵巧手

## [示例](examples/)

   **使用前请先将setting.yaml 配置文件根据实际需求进行相应修改该.**  
   **使用前请先将load\_write\_yaml.py文件第28行的yaml\_path ="" 改为config目录的绝对路径.**

## 通用

- \[0001-gui\_control(图形界面控制)]  
  开启ROS2 SDK后

bash 复制代码

```bash
# 新开终端
$ cd linker_hand_ros2_sdk/
$ source ./install/setup.bash
$ ros2 run gui_control gui_control
```

## L7

- [7001-action-group-show-ti(手指运动)](https://github.com/linkerbotai/linker_hand_ros2_sdk/blob/main/examples/L7/gesture/action-group-show-ti.py)

## L10

- [10001-action-group-show-normal(手指运动)](https://github.com/linkerbotai/linker_hand_ros2_sdk/blob/main/examples/L10/gesture/action-group-show-normal.py)