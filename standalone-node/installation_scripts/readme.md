# SPDX-FileCopyrightText: (C) 2025 Intel Corporation
# SPDX-License-Identifier: Apache-2.0

###########################
# README.MD file
###########################

build-hook-os-iso.sh is to
 i)  Generate the hook os kernel and initramfs file
 ii) Create the hook-os-iso with generated kernel and initramfs file
 iii) Create Standalone Installation tar file i.e sen-installation-files.tar.gz with all required files to 
      prepare bootable USB device

How to run:
    Go to frameworks.edge.one-intel-edge.edge-node.standalone-edge-node directory
    make build

    It will generate sen-installation-files.tar.gz file under frameworks.edge.one-intel-edge.edge-node.standalone-edge-node/installation_scripts/out directory

    Copy sen-installation-files.tar.gz linux system to prepare the bootable USB

bootable-usb-prepare.sh is to
   i) Generate the bootable USB device for booting the hook os on RAM and install OS on the edge node.
   ii) Please provide valid inputs for the scripts such as
       usb -> valid usb device with name ex. /dev/sda
       sen-installation-files.tar.gz -> this will be generated by make build command 
       proxy_ssh_config -> this is to configure proxy settings if the edge node behind the firewall 
			   ssh_key to your Linux device id_ras.pub key to do password less ssh connection with Edge node.
   
   ex: sudo ./bootable-usb-prepare.sh /dev/sda sen-installation-files.tar.gz proxy_ssh_config 

   iii) Once script creates the bootable USB device it read for installation.

 
