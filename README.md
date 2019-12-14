# kinnect-v1-install
This project is aim to install kinnect 
#install libfreenect
sudo apt-get install g++ python libusb-1.0-0-dev freeglut3-dev openjdk-8-jdk doxygen graphviz mono-complete//依赖项必要工具
 cd libfreenect
 mkdir build
 cd build
 cmake -L ..
 make
 sudo make install
 
#安装Udev规则
#将~/libfreenect/platform/linux/udev/下的51-kinect.rules复制到/etc/udev/rules.d/下

#安装Openni
#下载OpenNI-Bin-Dev-Linux-x64-v1.5.7.10.tar解压得到OpenNI-Bin-Dev-Linux-x64-v1.5.7.10文件夹
cd OpenNI-Bin-Dev-Linux-x64-v1.5.7.10
sudo ./install.sh

#安装Sensor
cd Sensor-Bin-Linux-x64-v5.1.2.1/
sudo ./install.sh

#安装NITE
cd NITE-Bin-Dev-Linux-x64-v1.5.2.23
sudo ./install.sh

#测试
roslaunch openni_launch openni.launch
#then add other terminal
cd ~/OpenNI-Bin-Dev-Linux-x64-v1.5.7.10/Samples/Bin/x64-Release
./NiViewer

#if you want to use kinnect in ROS please enter such code
sudo apt-get install ros-kinetic-freenect-launch
#test
roslaunch freenect_launch freenect.launch
