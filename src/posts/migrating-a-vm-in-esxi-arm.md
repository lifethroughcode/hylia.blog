---
layout: layouts/post.njk
title: Migrating a VM in ESXi ARM
date: 2021-12-03T09:26:24.052Z
tags:
  - raspberrypi
  - pi4
  - esxi
  - arm
  - esxiarm
  - datastore
---
#### **I'm going to show you how to add a new datastore to your ESXi-Arm Server and then move a Virtual Machine from the existing datastore to the new one we've added.** 

Some background - I currently run a Raspberry Pi4 8GB with ESXi-Arm as a home server. I did use a 256GB SD card to install ESXi onto, with the intention of using that for the VM's to run off but I don't think it's possible to actually access the rest of that memory as a datastore to install VM's - I will look into this more at a later date. 

As a temporary solution I used an old 100GB external drive I had lying about to create a datastore and run my VM's. It's been working great for what I need and mainly just runs PiHole at the moment which is set up as my DHCP server. However, I decided it would be useful to have my own cloud server where I can store files, photos, etc. therefore saving space on other devices and allowing the files to be accessible from any device I want, I chose to use NextCloud which is super easy to install with Ubunutu Server.

Before I did the NextCloud install, I needed to upgrade my storage; as a quick solution I got a 2TB external HDD and wanted to move my PiHole VM from the old drive onto this new one. 

> I found out the hard way that the RPi4 cannot power 2 external drives at the same time! 🤦

As standard the RPi4 gives 1.2A to all of the USB ports as a whole. Meaning it doesn't provide enough power for 2 external drives to be powered simultaneously. (There are modifications and ways around this, but I wouldn't recommend doing them.) 

As an easier fix, I got a mains powered USB hub which will allow me to plug up to 4 USB peripherals and power them instead of the Pi doing it, which then connects to the Pi using a single USB cable. I left the old HDD plugged into the Pi and plugged the new one into the USB hub, powered it on and connected it to the Pi. 

*Note: You can use a USB stick and an external HDD at the same time as it has lower power consumption.*