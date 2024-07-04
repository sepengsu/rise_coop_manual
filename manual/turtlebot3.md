## Turtlebot 관련 메뉴얼
1. Ubuntu: 20.04
2. ros: noetic (2025에 종료 예정)

### 1. Remote PC 설정
#### 1. install ubuntu 20.04 (searching으로 충분히 가능)
#### 2. install ros-noetic (프로젝트상 버전은 1.16.0) 
``` 
$ sudo apt update  
$ wget https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools/master/install_ros_noetic.sh  
$ chmod 755 ./install_ros_noetic.sh  
$ bash ./install_ros_noetic.sh  
```
#### 3. Install Dependent ROS Packages
```
$ sudo apt-get install ros-noetic-joy ros-noetic-teleop-twist-joy \
  ros-noetic-teleop-twist-keyboard ros-noetic-laser-proc \
  ros-noetic-rgbd-launch ros-noetic-rosserial-arduino \
  ros-noetic-rosserial-python ros-noetic-rosserial-client \
  ros-noetic-rosserial-msgs ros-noetic-amcl ros-noetic-map-server \
  ros-noetic-move-base ros-noetic-urdf ros-noetic-xacro \
  ros-noetic-compressed-image-transport ros-noetic-rqt* ros-noetic-rviz \
  ros-noetic-gmapping ros-noetic-navigation ros-noetic-interactive-markers
```
#### 4. Install TurtleBot3 Packages
크게 두가지 방법론이 존재 
##### 4.1. 24_rise_coop을 사용하지 않는 경우 
```
$ sudo apt install ros-noetic-dynamixel-sdk
$ sudo apt install ros-noetic-turtlebot3-msgs
$ sudo apt install ros-noetic-turtlebot3
``` 
##### 4.2. 24_rise_coop을 사용하는 경우 
turtlebot3, turtlebot3_simulations 패키지 있으면 삭제  
[24_rise_coop 설치 및 사용](https://github.com/sepengsu/rise_coop_manual/blob/main/manual/main.md)  
#### 5. Connection turtlebot3 and remote PC

