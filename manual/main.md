## 24_RISE_COOP 프로젝트 사용법

### 1. remote PC에 ROS 설치하기 
https://emanual.robotis.com/docs/en/platform/turtlebot3/quick-start/
1. Install ROS on Remote PC : guidline 3.1.2
2. Install Dependent ROS Pachages : Guidline 3.1.3
3. [Install package list]()

### 2. git cloning 
1. make catkin_ws folder and src
2. cd ~/catkin_ws/src/
3. git clone --recurse-submodules -b main https://github.com/sepengsu/24_rise_coop.git .
4. git remote remove origin

### 3. install turtleBot3 Backages from source
turtlebot 패키지 재구축
#### 1. remove the package
```
sudo apt remove ros-noetic-dynamixel-sdk
sudo apt remove ros-noetic-turtlebot3-msgs
sudo apt remove ros-noetic-turtlebot3
```
#### 2. 아애 없는 패키지 소스 다운로드 
```
git clone -b noetic-devel https://github.com/ROBOTIS-GIT/DynamixelSDK.git
git clone -b noetic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
```
#### 3. 소스 있는 것 수정을 위하여 다음 명령어 사용 
```
git clone -b noetic-devel https://github.com/ROBOTIS-GIT/turtlebot3.git turtlebot3_temp
rsync -av --ignore-existing turtlebot3_temp/ turtlebot3/
rm -rf turtlebot3_temp
```
```
cd ~/catkin_ws/src
git clone -b noetic-devel https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git turtlebot3_msgs_temp
rsync -av --ignore-existing turtlebot3_msgs_temp/ turtlebot3_msgs/
rm -rf turtlebot3_msgs_temp
```
#### 4. [종속된 패키지 설치하기](https://github.com/sepengsu/rise_coop_manual/blob/main/packlist/list.md)
<span style="color:red">이때 주의할 점은 지금 현재 모든 패키지를 설치하므로 오래걸리거나 잘못 설치될 가능성이 있다. 직접하자. </span>
#### 4. cd ~/catkin_ws
#### 5. <span style="color:red">catkin build </span>

## 초기 git repostiory 연결 방법 
```
1. catkin_ws 폴더를 작업폴더로 설정 (git init)
2. <span style="color:red">git remote add origin 새로운 git (git clone과 동일 주소 금지!!!)</span>
3. git fetch origin
4. git reset --hard origin/main
5. git checkout -b main
6. git push -u origin main 
```
