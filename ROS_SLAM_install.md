## Procedure to run OrbSLAM2

------------
Starts from a fresh Ubuntu 18.04 installation

1. install some dependencies

```
sudo apt update && apt install wget gnupg lsb-release curl python python-pip
```

2. setup the ros-melodic and rosdep
```
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
sudo curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
sudo apt update && sudo apt install -y ros-melodic-desktop-full
pip install rosdep
echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

3. install more dependencies
```
sudo apt install -y python-catkin-tools libgl1-mesa-dev libglew-dev libxkbcommon-dev libeigen3-dev ffmpeg python-pil.imagetk python-rosinstall python-rosinstall-generator python-wstool build-essential
```





4. install ROS
```
mkdir ~/ROS && cd ~/ROS
git clone --recursive https://github.com/stevenlovegrove/Pangolin.git
cd Pangolin 
./scripts/install_prerequisites.sh recommended
mkdir build && cd build
cmake ..
cmake --build .
```

6. change CMake version
```
cd ~/Download/
wget https://github.com/Kitware/CMake/releases/download/v3.23.1/cmake-3.23.1-linux-x86_64.tar.gz
tar -xvf cmake-3.23.1-linux-x86_64.tar.gz
sudo mv cmake-3.23.1-linux-x86_64 /opt/cmake-3.23.1
sudo ln -sf /opt/cmake-3.18.0/bin/* /usr/bin/
cmake --version 
```


5. install h264decoder

```
cd ~/ROS/ && git clone https://github.com/DaWelter/h264decoder.git && cd h264decoder/
mkdir build && cd build
cmake ..
make
```



