## 24_RISE_COOP 프로젝트 사용법
### 0. Remote PC 설정
1. Ubuntu: 20.04
2. ros: noetic (2025에 종료 예정)

### 1. remote PC에 ROS 설치하기 
https://emanual.robotis.com/docs/en/platform/turtlebot3/quick-start/
1. Install ROS on Remote PC : guidline 3.1.2
2. Install Dependent ROS Pachages : Guidline 3.1.3
3. [Install package list]()

### 2. git cloning 
1. make catkin_ws folder and src
2. cd ~/catkin_ws/src/
3. git clone --recurse-submodules -b main https://github.com/sepengsu/24_rise_coop.git .

### 3. install turtleBot3 Backages from source
1. sudo apt remove ros-noetic-dynamixel-sdk
2. sudo apt remove ros-noetic-turtlebot3-msgs
3. sudo apt remove ros-noetic-turtlebot3
4. git clone -b noetic-devel https://github.com/ROBOTIS-GIT/DynamixelSDK.git
5. git clone -b noetic-devel https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git
6. git clone -b noetic-devel https://github.com/ROBOTIS-GIT/turtlebot3.git
7. git clone -b noetic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
8. cd ~/catkin_ws && catkin_make

## 초기 git repostiory 연결 방법 
0. Start 진행
1. catkin_ws 폴더를 작업폴더로 설정 (git init)
2. <span style="color:red">git remote add origin 새로운 git (git clone과 동일 주소 금지!!!)</span>
3. git fetch origin
4. git reset --hard origin/main
5. git checkout -b main
6. git push -u origin main 
