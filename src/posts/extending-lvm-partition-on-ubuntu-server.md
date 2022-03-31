---
layout: layouts/post.njk
title: Extending LVM partition on Ubuntu Server
date: 2022-03-31T09:30:52.029Z
tags:
  - linux
  - ubuntu
  - ubuntuserver
  - lvm
  - partition
---
As you may know from previous posts, I have a NextCloud server running on a VM through ESXi. 

I originally set it up with 1.5TB of storage space, however Ubuntu did not utilise the full available disk amount, it only created a root partition of 200GB. This meant that it did not take long to fill the drive and my media was failing to upload to the server from my phone. 

These are the steps I took to extend the drive to the full 1.5TB of disk space - 

* I logged into ESXi and opened the terminal for my Ubuntu Server that runs NextCloud. 
* Run `sudo su` to make life easier and run all commands as sudo.
* Then run `df -h` you can also use `lsblk` (this will let you see the full filesystem layout).
* Here you can see how much space is available on your root partition. The one you want to extend should be called `/dev/mapper/ubuntu--vg-ubuntu--lv`
* You can run `vgdisplay` to see if there is any free space in the volume group.

Before running the following or doing any work on a live system I always recommend taking a backup of your VM! 

* To tell our server to use the full amount of allocated disk space we can run `lvextend -l +100%FREE /dev/mapper/ubuntu--vg-ubuntu--lv` as long as you have typed everything correctly it will say the size of the logical volume has changed and sucessfully resized.

Note: If you don't want to use the full disk amount, you can choose how much to extend by using `lvextend -l +100GB /dev/mapper/ubuntu--vg-ubuntu--lv` as long as you have the space you can change this to any amount you wish. 

* Now you need to update the file system to tell it that changes have been made. To do this run `resize2fs /dev/mapper/ubuntu--vg-ubuntu--lv`



And you're done!! 🎉



Now all you need to do is double check the file system and make sure it's updated! 

Run `df -h` again and if you've done it correctly then you will now see the "Size" and "Avail" columns have updated to reflect the full drive amount you extended by.



Hope this helped, and now you can be safe in the knowledge that all your cute dog photo's are being backed up!

![](/images/pexels-anna-shvets-4588049.jpg)



Credit to the following pages that provided me with the information to do this -

<https://askubuntu.com/questions/1269493/ubuntu-server-20-04-1-lts-not-all-disk-space-was-allocated-during-installation>

<https://www.linuxtechi.com/extend-lvm-partitions/>