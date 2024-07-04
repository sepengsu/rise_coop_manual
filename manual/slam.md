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

### 현재 상황
1. simulation 상에서는 imu가 사용하지 못함 -->odm을 찾을 수 없음 