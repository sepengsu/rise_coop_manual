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
먼저 위의 4.1 에서 설치한 것들 remove 해야함 
[24_rise_coop 설치 및 사용](https://github.com/sepengsu/rise_coop_manual/blob/main/manual/main.md)  
#### 5. Connection turtlebot3 and remote PC
 !ifconfig으로 ip 각각 설정함  
 만약에 Simulation 상으로 한다면 다음과 같이 설정 
```
export ROS_MASTER_URI=http://localhost:11311
export ROS_HOSTNAE=127.0.0.1
``` 

#### 6. connection wifi in turtlebot3
##### 6.1. wifi 동굴을 사용하여 turtlebot3와 인터넷 연결을 활성화 한다.
```
sudo nano /etc/wpa_supplicant/wpa_supplicant.conf     
``` 
위 코드를 이용하여 와이파이 아이디, 비밀번호를 수정한다.
```
sudo systemctl daemon-reload # optional
sudo systemctl restart networking
sudo systemctl restart wpa_supplicant 
sudo service network-manager restart
```
##### 6.2. 아래와 같이 NTP와 RTC가 되어 있는지 확인한다. 
```
timedatectl
ping google.com # 연결되어 있는지 확인하기 
```  
만약에 문제가 계속 생긴다면 다음을 확인한다.
```
sudo nano /etc/resolv.conf # nameserver 8.8.8.8 와 8.8.4.4 있는지 확인 
sudo nano /etc/hosts # host 정보 확인 
```
