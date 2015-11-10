---
title: Upgrading CyanogenMod or any other Android ROM on an encrypted Nexus 4 device
author: Tim Kleinschmidt
date: 2013-07-30 22:02:00
category: Android
---

I got a following problem that I was not be able to update my phone from my recovery mode. I'm using [ClockworkMod](http://www.clockworkmod.com/rommanager).

So I searched around the web and found a very easy way to update my Nexus 4

1.  Connect your Nexus with the USB cabel with your computer
2.  Download the CyanogenMod package you want to install, from [http://get.cm/?device=mako](http://get.cm/?device=mako)
3.  Boot the recovery mode
4.  Navigate to **install zip**
5.  Navigate then to **insall zip from sideload**
6.  You need now the **Android Platform Tools**
7.  Open your terminal now
8.  Type now **&quot;adb sideload cyanogenmod.zip&quot;** (cyanogenmod.zip is the downloaded package from the second step)
9.  After it reboot you phone

Bonus Tip:
*   If you have problems with the Wifi on your Nexus 4 try the [WifiFix](http://forum.xda-developers.com/showthread.php?t=2300873) from kalo86 on the same way what is describe in points above
