---
layout: post
published: false
title: automate-your-tv
subtitle: Integrate your Open Source Set-top box with Home Assitant
---
I have been using [Home Assistant][1] on my Raspberry Pi for the past few months. This is my DIY home automation pet project, and I will be posting more about it in future.

Today, I want to show you something which is not offically part of Home Assistant, yet, and that is adding support for Enigma2 based set top box receivers. Examples include devices from Vu (Duo, Duo2, Uno, etc) and lots of manufacturers who support the open sourced images based on Enigma2, such as OpenVix and Black Hole.

I developed a python pip module, called [openwebif.py][2], which interfaces with the REST APIs built into OpenWebIf. OpenWebIf is the web interface on top of all Enigma2 based receivers.

I then developed a custom **media_player** component for Home Assistant, which allows basic control of the unit and the TV. The component supports:

1. Power standby/wake toggle (on/off)
2. Volume set
3. Mute/unmute
4. Query current program info such as:
	- TV station active, 
    - Programme Name & Description
    - Picon (channel icon) for the station

![Home Assistant Enigma2 Preview]({{site.baseurl}}/img/posts/enigma2.png)

To install the component, you place the file `enigma2.py` inside your folder `~/custom_components/media_player` which is inside your Home Assistant configuration directory.

Then, in your `configuration.yaml` file, add a new entry like this:
```yaml
media_player:
   - platform: enigma2
     host: 10.10.10.4
     name: Vu Duo2
     icon: mdi:satellite-variant
```

[1]: https://home-assistant.io
[2]: https://github.com/fbradyirl/openwebif.py
