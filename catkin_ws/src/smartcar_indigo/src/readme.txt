sudo update-locale LANG=C LANGUAGE=C LC_ALL=C LC_MESSAGES=POSIX

export LANGUAGE=en_US.UTF-8
export LANG=en_US.UTF-8
export LC_ALL=en_US.UTF-8
sudo locale-gen en_US.UTF-8
sudo dpkg-reconfigure locales

sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu trusty main" > /etc/apt/sources.list.d/ros-latest.list'
sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net --recv-key 421C365BD9FF1F717815A3895523BAEEB01FA116

sudo apt-get update
sudo apt-get install vim
sudo apt-get install git rpm
sudo apt-get install libpython2.7-dev python-rosinstall
sudo apt-get install ros-indigo-desktop-full
sudo apt-get install ros-indigo-ros-base
sudo apt-get install ros-indigo-navigation
sudo apt-get install ros-indigo-slam-gmapping
sudo apt-get install ros-indigo-sick-tim
sudo apt-get install ros-indigo-serial
sudo apt-get install ros-indigo-ecl
sudo apt-get install ros-indigo-diagnostic-updater
sudo apt-get install ros-indigo-urdf-tutorial
sudo apt-get install ros-indigo-arbotix-*
sudo apt-get install python-rosdep
sudo rosdep init
rosdep update


mkdir -p catkin_ws/src
cd catkin_ws/src/
catkin_init_workspace 
cd ..
catkin_make

echo "source /opt/ros/indigo/setup.bash" >> ~/.bashrc  
echo "source  ~/github/Indigo/catkin_ws/devel/setup.bash" >> ~/.bashrc  

source ~/.bashrc 


cd catkin_ws/src/
catkin_create_pkg  smartcar_indigo  std_msgs rospy roscpp urdf

mkdir include launch urdf

sh smartcar1.0_launch.sh

