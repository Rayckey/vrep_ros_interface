# ROS Interface plugin for V-REP

### Compiling

1. Download
```
$ git clone --recursive https://github.com/Rayckey/v_repExtRosInterface.git
```
2. Edit `meta/messages.txt` and `meta/services.txt` if you need to include more ROS messages/services. You need to specify the full message/service type, i.e. geometry_msgs/Twist rather than Twist.
3. Edit `set(ENV{VREP_ROOT} ~/V-REP_PRO_EDU_V3_5_0_Linux)` in `CMakeLists.txt` to the path of V-REP installation, and comment `link_directories("/opt/ros/lunar/lib")` if using older versions 
4. Clone XR1_vrep_ros, return to work space and build using catkin build (catkin make may cause issues)
```
$ catkin build
```
5. IMPORTANT! After compiling, copy `libv_repExtRosInterface.so` from `WORKSPACE/devel/lib/` to V-REP root folder, and do so whenever the `meta/messages.txt` or `meta/services.txt` files have been modified



### Dependencies
1. For catkin build to work, some packages may need to be installed via apt-get, which include:

# Essentials
```
$ sudo apt-get install python-catkin-tools python-rosdep python-rosinstall-generator python-wstool python-rosinstall build-essential xsltproc
```
# cakin_tools
```
$ sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu `lsb_release -sc` main" > /etc/apt/sources.list.d/ros-latest.list'
$ wget http://packages.ros.org/ros.key -O - | sudo apt-key add -
$ sudo apt-get update
$ sudo apt-get install python-catkin-tools
```

# v_repExtRosInterface
