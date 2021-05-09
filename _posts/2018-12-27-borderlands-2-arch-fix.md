---
layout: post
title:  "Borderlands 2 Arch Fix"
pin: true
---

This is a write up on how I fixed why borderlands 2 would not launch.
 
So the symptom was that when I tried to launch Borderlands 2 from the steam client all it would do is act like it was going to open then it would crash before the game would open.
 
The Problem
Turns out the game needed was libopenal.so.1
 
  
The Fix
The fix was to allow execution of the game from the installation folder and create a script that executes the game with a LD_PRELOAD.
 
Note : If you are using GNOME you can use Main Menu to edit the shortcut to run this script
 
The Script is as follows (other than you need to change the locations to the correct locations for you system)
 
 ```bash
 #!/bin/bash
 ## Borderlands 2 Fix
 ### Uses LD_Preload to load what is missing for 
 ## Written by CJ S
 LD_PRELOAD='$HOME/.local/share/Steam/ubuntu12_32/steam-runtime/i386/usr/lib/i386-linux-gnu/libopenal.so.1'
 cd "/path/to/Borderlands 2/folder"
 ./Borderlands2
 ```
