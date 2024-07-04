### 명령어 순서

#### 1. ros 실행 
```
roscore
```
#### 2. turtlebot3 bringup
```
ssh pi@192.168.4.1
roslaunch turtlebot3_bringup turtlebot3_robot.launch
```
#### 3. key mode 
```
roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```
#### 4. slam using cartographer
```
roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=cartographer
```
#### 5. Visualization 
```
rviz
```