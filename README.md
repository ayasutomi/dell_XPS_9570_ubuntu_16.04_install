# Dell XPS 9570 Ubuntu 16.04 install and initial config

This repository is to store my personal memos about the installation and initial configuration 
of Ubuntu 16.04 LTS in the notebook Dell XPS 9570.

## PC Specifications
- **Manufacturer**: Dell
- **Model**: XPS 15 9570
- **System type**: x64-based PC
- **OS**: Windows 10 Home
- **Processor**: Intel(R) Core(TM) i7-8750H CPU @ 2.20GHz, 2208 Mhz, 6 Core(s), 12 Logical Processor(s)
- **BIOS Version/Date**:	Dell Inc. 1.9.1, 4/8/2019
- **Memory (RAM)**: 16.0 GB DDR4 at 2666 Mhz
- **Storage**: 512 GB PCIe SSD
- **Graphic Card**: NVIDIA GeForce GTX 1050Ti 4GB GDDR5

## Ubuntu Installation from Windows 10

1. Download Ubuntu 16.04 LTS ISO file:
http://releases.ubuntu.com/16.04/

2. Create ubuntu bootable stick with procedure in:
https://tutorials.ubuntu.com/tutorial/tutorial-create-a-usb-stick-on-windows#0

3. Disable fast start up on Windows 10 with procedure in: https://www.windowscentral.com/how-disable-windows-10-fast-startup

4. Enable AHCI mode with procedure in: https://medium.com/@peterpang_84917/personal-experience-of-installing-ubuntu-18-04-lts-on-xps-15-9570-3e53b6cfeefe

5. Install ubuntu:
  - Procedure: https://www.itzgeek.com/how-tos/linux/ubuntu-how-tos/install-ubuntu-16-04-with-screenshots.html
  - Disk Space:
  
     Mount Point | Size 
     --- | --- 
     swap  | 16 GB   
     /boot  | 1 GB    
     /     | 63 GB   
     /home | 120 GB  

    - References:
      - https://help.ubuntu.com/community/DiskSpace
      - https://superuser.com/questions/65115/what-sizes-should-you-allocate-to-the-boot-home-and-swap
      - https://itsfoss.com/swap-size/

6. Install NVIDIA driver:
  - Add the graphics drivers PPA:
    ```
    sudo add-apt-repository ppa:graphics-drivers/ppa
    ```
  - Update and upgrade the system:
    ```
    sudo apt update
    sudo apt upgrade
    ```
  - Check the latest nvidia driver:
    ```
    ubuntu-drivers list
    ```
  - Install the latest driver:
    ```
    sudo apt install nvidia-418
    ```
  - Check installation:
  
  - References:
    - https://www.maketecheasier.com/install-nvidia-drivers-ubuntu/
    - http://www.linuxandubuntu.com/home/how-to-install-latest-nvidia-drivers-in-linux
 

## Additional Packages Installation

### ROS kinetic and Gazebo 7.0

- Run the following to install ROS kinetic and related tools :
    ```
    sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

    sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654
    
    sudo apt update
    
    sudo apt install ros-kinetic-desktop-full
    
    sudo rosdep init
    
    rosdep update
    
    echo "source /opt/ros/kinetic/setup.bash" >> ~/.bashrc
    
    source ~/.bashrc
    
    sudo apt install python-rosinstall python-rosinstall-generator python-wstool build-essential python-catkin-tools
    ```

- Run the following to update Gazebo 7.0 previously installed with ROS kinetic:
    ```
    sudo sh -c 'echo "deb http://packages.osrfoundation.org/gazebo/ubuntu-stable `lsb_release -cs` main" > /etc/apt/sources.list.d/gazebo-stable.list'

    wget http://packages.osrfoundation.org/gazebo.key -O - | sudo apt-key add -

    sudo apt update
    
    sudo apt upgrade
    ```

- Ref: http://wiki.ros.org/kinetic/Installation/Ubuntu
- Last update: 2019/7/14


## Error Handling

### Windows does not boot:
- Description: Windows gets stuck on loading and PC restarts. Windows error manager shows up sometimes.
- Solution: Click in 'advanced options' and 'Continue to Windows 10'. This will restart the PC and when choosing Windows 10 it will boot.
- Last update: 2019/5/10



  
  
