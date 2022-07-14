---
layout: layouts/post.njk
title: ProtonVPN kill switch woes in Ubuntu
date: 2022-07-14T12:10:00.563Z
tags:
  - ubuntu
  - protonvpn
  - vpn
  - killswitch
  - linux
---
Yesterday I turned my laptop on, like I would any other day. Except this time, I had no internet - well, it was connected to the Wi-Fi, I could ping local devices, as well as 1.1.1.1/8.8.8.8 but I could not get onto any web pages. 

My laptop is running Ubuntu 21.10 and has ProtonVPN installed which is set up with a kill switch, so whenever it's not connected to the VPN it's not going to allow an internet connection. This is great, and a feature I used permanently with no issues when I was with PIA. Annoyingly, ProtonVPN does not work so well on Ubuntu currently. 

I am forever having issues getting the app to open, and usually it will open the app but continue to spin around in app while it loads - and proceeds to not load. 

Yesterday, Proton continued spinning, and spinning, and (you guessed it!) spinning. I restarted the laptop several times, tried running updates, and a bunch of other troubleshooting. 

I was aware this was likely going to be related to the kill switch, so without much thought I deleted all ProtonVPN packages (protonvpn-cli, protonvpn-gui, etc.). If it's not installed it won't cause any problems, right? Wrong.

To uninstall I used the following commands as you would with most programs on Linux - 

`sudo apt-get remove PackageNameHere`

`sudo apt-get purge PackageNameHere`

`sudo apt-get autoremove`

If you have also done this, then congrats, you still won't have internet connection. Maybe this is by design to keep your IP secure, either way it's not obvious on how to fix it.

If you run the following command from the terminal - 

`nmcli dev status`

You will likely see under device **ipv6leakintrf0** connected, and next to it under connection **pvpn-ipv6leak-protection** here is the problem, it looks like Proton even after death is still protecting the computer. 

(Now to note, Proton VPN servers are compatible with IPv4 only, so all IPv6 connections are blocked by default. However the article that stated that was written in 2018, so it may have changed since)

I'm not going to pretend I've done much research on this so can't give a definitive answer on why this one ipv6 connection is blocking ipv4 also, but I can tell you how to fix it. 

✨The Magic Fix ✨

`nmcli c delete pvpn-ipv6leak-protection`

This is telling the network manager cli to delete the connection for this IPv6 leak protection. 

Now all being well your computer should connect again and you can go ahead and reinstall Proton VPN (and maybe leave the kill switch off for now).

Please note I absolutely love ProtonVPN and will continue to recommend them. On my Windows machine I have had no problems with the kill switch ever. But it can be rather buggy on Ubuntu from my experience, and this took me a little while to troubleshoot. 

Big thanks to Reddit user "scotsmanintoon" who posted the command that fixed this for me. 💖