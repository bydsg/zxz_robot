根据b站赵旭左老师的视频做的仿真功能包，运行后可以提供可视化差速小车模型、里程计数据（/odom）、可以通过发布cmd_vel控制小车运动<br>
此功能包可以提供最简单的仿真平台<br>

功能包介绍：<br>
urdf_by提供小车物理模型建模<br>
key_control提供小车控制节点<br>
arbotix_ros 为小车提供cmd_vel和odom接口<br>
<br>
<br>
使用方法：<br>
mkdir -p zxz_robot/src 		#创建功能包<br>
cd zxz_robot				#进入功能包<br>
将下载的三个功能包拷贝到src下<br>
返回到 zxz_robot下<br>
catkin_make 				#编译<br>
source ./devel/setup.bash		#刷新环境变量<br>
<br>
<br>
roslaunch urdf_by demo01.launch 	#运行仿真环境，此时已有odom和cmd_vel接口<br>
rosrun key_control key 		#运行键盘控制节点 wasd控制小车移动 shift加速<br>
<br>
###################<br>
若运行roslaunch urdf_by demo01.launch 时提示arbotix_ros启动失败，可以尝试将<br>
arbotix_ros/arbotix_python/bin/arbotix_driver下第一行#!/usr/bin/env python3<br>
改为#!/usr/bin/env python2.7<br>
保存编译再次运行roslaunch urdf_by demo01.launch <br>
