### 실행 방법 
여기서 simulation이 아닌 turtlebot과 연결하여 실행한다. 
#### 1. roscore 실행
```
roscore
```
#### 2. turtlebot bringup
```
ssh pi@192.168.4.1
roslaunch turtlebot3_bringup turtlebot3_robot.launch
```

#### 3. realsense camera 실행
```
ssh pi@192.168.4.1

roslaunch realsense2_camera rs_camera.launch \
enable_color:=true \
enable_depth:=true \
enable_infra1:=false \
enable_infra2:=false \
enable_imu:=false \
enable_fisheye:=false \
depth_width:=480 \
depth_height:=270 \
depth_fps:=15 \
color_width:=424 \
color_height:=240 \
color_fps:=15 \
enable_pointcloud:=true \
pointcloud_texture_stream:=RS2_STREAM_COLOR \
pointcloud_texture_index:=0 \
align_depth:=true
```
#### 4. key mode 실행
```
roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```
#### 5. rtabmap 실행 
```
roslaunch rtabmap_my rtabmap_pointcloud.launch
```