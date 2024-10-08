# Nano-AC600
 TP-Link Nano AC600 (Archer T2U)​ Adapter driver for Linux


- sudo apt update && sudo apt upgrade
- sudo apt-get install dkms
- sudo apt-get install bc
- sudo apt-get install rsync
- sudo apt-get install git
- sudo apt update
   
--
 
- git clone https://github.com/clashhsalc/8821au-20210708.git
- cd 8821au-20210708

-- 
  
- VER=$(sed -n 's/\PACKAGE_VERSION="\(.*\)"/\1/p' dkms.conf)
- sudo rsync -rvhP ./ /usr/src/rtl88x2bu-${VER}
- sudo dkms add -m rtl88x2bu -v ${VER}
- sudo dkms build -m rtl88x2bu -v ${VER}
- sudo dkms install -m rtl88x2bu -v ${VER}
- sudo modprobe 8821au
- reboot
