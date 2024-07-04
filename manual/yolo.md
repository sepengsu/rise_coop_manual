### 실행 방법 

#### 1. roscore 실행
```
roscore
```
#### 2. realsense camera 실행
```
ssh pi@192.168.4.1

roslaunch realsense2_camera rs_camera.launch \
enable_color:=true \
enable_depth:=false \
enable_infra1:=false \
enable_infra2:=false \
enable_imu:=false \
enable_fisheye:=false \
color_width:=424 \
color_height:=240 \
color_fps:=15 \
enable_pointcloud:=false
```

#### 3. turtlebot3 bringup
```
ssh pi@192.168.4.1
roslaunch turtlebot3_bringup turtlebot3_robot.launch
```
#### 4. yolo 실행
```
ssh pi@192.168.4.1
roslaunch darknet_ros darknet_ros.launch network_param_file:=$(rospack find darknet_ros)/config/yolov2-tiny.yaml
```
#### 5. key 실행 
```
roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```
#### 6. rviz 실행
```
rviz
```
