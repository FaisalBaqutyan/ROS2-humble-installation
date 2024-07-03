# ROS2-humble-installation

## upload Ubuntu 22.04 on a virtual machine


first, to install ROS2 you have to download a virtual machine and then download Ubuntu to this virtual machine then install ROS2 in Ubuntu

the virtual machine used here is Oracle VM and for ROS2 humble we have to download Ubuntu 22.04

to create an Ubuntu on the virtual machine first we will click new then the type we will choose Linux and the version Ubuntu (64-bit)

![Screenshot 2024-07-03 134237](https://github.com/FaisalBaqutyan/ROS2-humble-installation/assets/174335196/d1420119-6c2b-495b-aa28-82afde929861)

next, we will choose a Base memory and processor suitable for the PC

![Screenshot 2024-07-03 134324](https://github.com/FaisalBaqutyan/ROS2-humble-installation/assets/174335196/ca53f66d-5b04-4f3b-a7bb-df7395eaba5c)

then the virtual hard disk should be around 30GB 

![Screenshot 2024-07-03 134343](https://github.com/FaisalBaqutyan/ROS2-humble-installation/assets/174335196/cb11d047-987d-490a-a7dd-0c977fad0ff9)

finally, we will click next and then finish 

to upload Ubuntu in this virtual machine we should go to settings then storage then choose Ubuntu 22.04 from here

![Screenshot 2024-07-03 134846](https://github.com/FaisalBaqutyan/ROS2-humble-installation/assets/174335196/c1b91386-91e8-4ab2-a34f-82882a1b3b43)


## install ROS2 humble on Ubuntu

after we upload Ubuntu to the virtual machine we can run it easily  

next, we will open a terminal on Ubuntu 

![Screenshot from 2024-07-03 14-10-32](https://github.com/FaisalBaqutyan/ROS2-humble-installation/assets/174335196/a80d9dab-21f5-4de6-b1f0-9b921e08b14f)

next we will copy and paste these codes one by one in the terminal 


```
locale  # check for UTF-8

sudo apt update && sudo apt install locales
sudo locale-gen en_US en_US.UTF-8
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
export LANG=en_US.UTF-8

locale  # verify settings
```

```
sudo apt install software-properties-common
sudo add-apt-repository universe
```

```
sudo apt update && sudo apt install curl -y
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg
```

```
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null
```

```
sudo apt update
```

```
sudo apt upgrade
```

```
sudo apt install ros-humble-desktop
```

```
sudo apt install ros-humble-ros-base
```

```
sudo apt install ros-dev-tools
```

that's how you can install ROS2 easily now we can try an examble to make sure that ROS2 humble is installed without any problem 

we will open two terminal

in the first terminal we will copy this code 

```
source /opt/ros/humble/setup.bash
ros2 run demo_nodes_cpp talker
```

and in the second terminal we will copy this code 

```
source /opt/ros/humble/setup.bash
ros2 run demo_nodes_py listener
```

now we should see this 

![Screenshot from 2024-07-03 14-38-07](https://github.com/FaisalBaqutyan/ROS2-humble-installation/assets/174335196/ee9047a1-511f-42e0-a0ad-9a8a152e98ba)

that's how we can install ROS2 humble
