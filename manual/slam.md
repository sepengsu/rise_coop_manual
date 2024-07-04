### 명령어 순서

#### 1. 
bash 4개 생성 
#### 2. 각각 bash 
```
roscore
```
```
ssh pi@192.168.4.1
roslaunch turtlebot3_bringup turtlebot3_robot.launch
```
```
roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```
```
roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=cartographer
```
```
rviz
```