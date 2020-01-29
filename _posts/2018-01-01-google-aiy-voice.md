---
title: Google Aiy Voice
date: 2018-01-01 00:00:00 Z
permalink: "/google-aiy-voice"
layout: post
excerpt: Create your own Echo Dot using Google AIY Voice Kit
images:
- url: "/assets/Cover11th.png"
---

## Adventures with Google AIY Voice Kit

### Raspberry Pi setup notes
1. Choose an 8 GB or larger SD card and fastest possible (class 10 or higher)
2. Run `sudo raspi-config` and change the following:
	- Update 
	- Change default user password
    - Change hostname
    - Overclock: set to `Turbo`
    - Localization: set `Timezone`
    - Interfacing Options: enable `ssh`, `camera`
    - Advanced Options: Expand Filesystem
    - Boot Options: Console AutoLogin
