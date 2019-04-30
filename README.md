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

- Download Ubuntu 16.04 LTS ISO file:
http://releases.ubuntu.com/16.04/
- Create ubuntu bootable stick with procedure in:
https://tutorials.ubuntu.com/tutorial/tutorial-create-a-usb-stick-on-windows#0
- Disable fast start up on Windows 10 with procedure in: https://www.windowscentral.com/how-disable-windows-10-fast-startup
- Enable AHCI mode with procedure in: https://medium.com/@peterpang_84917/personal-experience-of-installing-ubuntu-18-04-lts-on-xps-15-9570-3e53b6cfeefe
- 
- Disk Space:
  - Chosen sizes:
    - Swap: 16 GB
    - /boot: 1 GB
    - /: 63 GB
    - /home: 120 GB
  - References:
    - https://help.ubuntu.com/community/DiskSpace
    - https://superuser.com/questions/65115/what-sizes-should-you-allocate-to-the-boot-home-and-swap
    - https://itsfoss.com/swap-size/
  
  
