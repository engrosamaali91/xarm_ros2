# xarm_ros2

#Installation 
- Install ros2 https://docs.ros.org/en/ros2_documentation/humble/Installation.html
- Install moveit https://moveit.ros.org/install-moveit2/binary/


# How to use 
Create a workspace
```shell
# Skip this step if you already have a target workspace
$ cd ~
$ mkdir -p dev_ws/src
```
Obtain source code of "xarm_ros2" repository
```shell
# Remember to source ros2 environment settings first
$ cd ~/dev_ws/src
# DO NOT omit "--recursive"，or the source code of dependent submodule will not be downloaded.
# Pay attention to the use of the -b parameter command branch, $ROS_DISTRO indicates the currently activated ROS version, if the ROS environment is not activated, you need to customize the specified branch (foxy/galactic/humble)
$ git clone https://github.com/xArm-Developer/xarm_ros2.git --recursive -b $ROS_DISTRO
```

Update "xarm_ros2" repository
```shell
$ cd ~/dev_ws/src/xarm_ros2
$ git pull
$ git submodule sync
$ git submodule update --init --remote
```
Install dependencies

```shell
# Remember to source ros2 environment settings first
$ cd ~/dev_ws/src/
$ rosdep update
$ rosdep install --from-paths . --ignore-src --rosdistro $ROS_DISTRO -y
```
Build xarm_ros2

```shell
# Remember to source ros2 and moveit2 environment settings first
$ cd ~/dev_ws/
# build all packages
$ colcon build

# build selected packages
$ colcon build --packages-select xarm_api
```
source the environment setup script before running any applications in xarm_ros2

```shell
$ cd ~/dev_ws/
$ source install/setup.bash
```


【simulated】Launch moveit, controlling robot in rviz.
```shell
$ cd ~/dev_ws/
# For xArm(xarm6 as example): set 'add_gripper=true' to attach xArm gripper model
$ ros2 launch xarm_moveit_config xarm6_moveit_fake.launch.py [add_gripper:=true]
```
Either source gazebo or add the source command in .bashrc file
```shell
/usr/share/gazebo/setup.sh
```
