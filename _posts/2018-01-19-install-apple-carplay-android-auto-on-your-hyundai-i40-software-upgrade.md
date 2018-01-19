---
layout: post
published: true
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
![]({{site.baseurl}}/img/apple-carplay-ios.png)

Recently, I began looking into how I could get Apple Carplay installed on my 2016 Hyundai i40. I could see Hyundai UK [were tweeting](https://twitter.com/Hyundai_UK/status/881783938192224257) that a free software update was available for any SE Nav model since Nov 2015. However, unlike our US counterparts, this was not a publically accessible upgrade. It must be done by a Hyundai dealer.

So I rang my local dealer here in Galway, and they gave me a quote for €100 to do the update. The €100 was apparently to cover the "labour" costs in doing the update. _Hummm..._

As a software engineer myself, I thought I'd search the web for a way to carry this out myself, since I was pretty sure that once I could **get** the firmware files, I would be able to figure out **how** to install the update.

I eventually came across a Russian [forum](https://www.drive2.ru/l/492401715044155399), where a link to download the firmware was posted, along with some instructions. I thought it might be good for me to re-post those instructions in english here for anyone wanting to do it. Here goes...

## Disclaimer
**WARNING: If you carry out this car firmware upgrade, you do so at your own risk. This may void you warranty. Please do your own research if you are worried about this.**

## What you will need
- A USB Stick (1GB or more will do). Formatted for FAT32.
- A ballpoint pen.
- A PC to download the firmware.
- The current version of software on your vehicle. 
	- To find this out, on your car touchscreen, go to `All Menus`>`System Info`(scroll to the bottom to see that) and then take note of the **"S/W ver."** field. 
	- The version should begin with `ST.XXXX.`
    - Note the letters after `ST.`
    - That will determine which folder you want to use in step 4 below...

## System Update Procedure

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/ssNr4ZbwEnU/0.jpg)](https://www.youtube.com/watch?v=ssNr4ZbwEnU)

**Note:** I took a [video of the in-car parts of the procedure and posted to youtube here](https://youtu.be/ssNr4ZbwEnU), which may be of help. 

1. Download and [extract the firmware files from here](https://yadi.sk/d/2P-O8kHN3RNyd5). _Also [backed-up here](https://drive.google.com/file/d/1HmzoOO1BoCplOSoNuhXOsZouI2vDoO-a/view?usp=sharing)._
2. You will see 4 folders: `st_vf`, `st_vfia`, `st_vfsd` and `st_vfsdia` 
3. To know which one to open, take a look at the version on your vehicle at present.
    - Note the letters after `ST.`
    - That will determine which folder you want to use.
4. For me it was `vfsdia`. So, I looked inside the `st_vfsdia` folder and saw an `update` folder.
5. Insert your USB Stick into your PC, and ensure it is formatted as FAT32 (most memory sticks already are).
6. Copy the `update` folder directly over to the USB Stick. _note that you should **not** use the car navigation SD card for this, as it will not work for a system update._
7. At this point, when you look at the USB drive on your PC, you should see the `update` folder at the root of the drive.
8. Eject the USB stick from your PC and go to the car.
9. **Important:** Start your engine and leave it running for all the rest of the procedure
10. Insert the USB stick into the usb slot in front of the gear stick.
11. On your car touchscreen, go to `All Menus`>`System Info`(scroll to the bottom to see that) and press the `Update` button.
12. Confirm the popup by pressing the `OK` button.
13. Sit back and relax. The update will take 30-40 minutes in total. Ensure you leave the engine running all the time during the update.
14. After about 10 minutes, you may see a system error (code `109`), as I did. 
	- You need to remove the USB stick at this point.
	- Now use your ballpoint pen to press the reset button for 5 seconds. The reset button is tiny and you can find it just to the right of the CD slot above the touchscreen.
15. The reset will reboot the system and continues the upgrade. The USB stick is no longer needed from now on, so you can put it away in your pocket.
16. The update will take another 20-30 minutes, so head away and grab a cup of tea.

In the end, you will have the latest firmware installed and you can plug in your smartphone to enjoy Android Auto or Apple Carplay.

**Note** I take no credit whatsoever for the firmware. It was not created by me. I simply downloaded it and followed Google translated instructions from users [@Sernaiko](https://www.drive2.ru/users/sernaiko/) and [@raler](https://www.drive2.ru/users/raler/) over at [drive2.ru](https://www.drive2.ru/l/492401715044155399/). Thank you to those guys for sharing the details on how this can be done.
