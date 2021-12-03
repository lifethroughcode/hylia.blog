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
I currently run a Raspberry Pi4 8GB with ESXi-ARM as a home server. I did use a 256GB SD card to install ESXi onto, with the intention of using that for the VM's to run off but I don't think it's possible to actually access the rest of that memory as a datastore to install VM's - I will look into this more at a later date. 

As a temporary solution I used an old 100GB external drive I had lying about to create a datastore and run my VM's. It's been working great for what I need and mainly just runs PiHole at the moment which is set up as my DHCP server. However, I decided it would be useful to have my own cloud server where I can store Files, Photos, etc. therefore saving space on other devices and allowing the files to be accessible from any device I want, I chose to use NextCloud which is super easy to install with Ubunutu Server



I'm going to show you how to add a new datastore to your ESXi ARM and then move a Virtual Machine from the existing datastore to the new one we've added.