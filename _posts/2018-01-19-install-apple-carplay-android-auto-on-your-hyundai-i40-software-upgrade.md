---
layout: post
published: false
title: Install Apple Carplay & Android Auto on your Hyundai i40 (Software Upgrade)
tags:
  - apple carplay
  - hyundai i40
  - europe
  - uk
  - ireland
  - russia
  - germany
  - eu
  - android auto
  - firmware upgrade
  - software update
  - ST.VFSDIA.EU.E517.160926
subtitle: >-
  Details on how you can manually install the latest software on your European
  Hyundai i40 to enable Apple Carplay and Android Auto support.
date: '2018-01-19'
---
## DIY Software Update

Recently, I began looking into how I could get Apple Carplay installed on my 2016 Hyundai i40. I could see Hyundai UK [were tweeting](https://twitter.com/Hyundai_UK/status/881783938192224257) that a free software update was available for any SE Nav model since Nov 2015. However, unlike our US counterparts, this was not a publically accessible upgrade. It must be done by a Hyundai dealer.

So I rang my local dealer here in Galway, and they gave me a quote for €100 to do the update. The €100 was apparently to cover the "labour" costs in doing the update. _Hummm..._

As a software engineer myself, I thought I'd search the web for a way to carry this out myself, since I was pretty sure that once I could **get** the firmware files, I would be able to figure out **how** to install the update.

I eventually came across a Russian forum, where a link to download the firmware was posted, along with some instructions. I thought it might be good for me to re-post those instructions in english here for anyone wanting to do it. Here goes...

1. Download and [extract the firmware files from here](https://yadi.sk/d/2P-O8kHN3RNyd5).
2. You will see 4 folders: `st_vf`, `st_vfia`, `st_vfsd` and `st_vfsdia` 
3. On your car touchscreen, go to "All Menus">"System Info"(scroll to the bottom to see that) and then take note of the **"S/W ver."** field. 
	- The version should begin with `ST.XXXX.`
    - See what letters are there after `ST.`
    - That will determine which folder you want to use.
    
4. For me it was `vfsdia` so I looked inside the `st_vfsdia` folder and saw an `update` folder.
5. Get a USB Stick, and ensure it is formatted as FAT32 (most memory sticks already are).
6. Copy the `update` folder directly over to the USB Stick. _note that you should **not** use the car navigation SD card for this, as it will not work for a system update._
7. At this point, when you look at the USB drive on your PC, you should see the `update` folder at the root of the drive.
8. Eject the USB stick from your PC and go to the car.
9. **Important:** Start your engine and leave it running for all the rest of the procedure
10. 