---
layout: post
published: true
title: Automate Your TV
subtitle: Integrate your Open Source Set-top box with Home Assistant
tags:
  - tech
  - iot
  - home automation
  - home assistant
  - enigma2
  - openvix
share-img: img/posts/enigma2-hass.png
---
I have been using [Home Assistant][1] on my Raspberry Pi for the past few months to power my home automation. 

Today, I want to share with you something which is not offically part of Home Assistant, yet, and that is adding support for Enigma2 based set top box receivers. Examples include devices from Vu (Duo, Duo2, Uno, etc) and lots of manufacturers who support the open sourced images based on Enigma2, such as OpenVix and Black Hole.

At present, the new component supports:

1. Power standby/wake toggle (on/off)
2. Select next/prev channel
3. Volume set
4. Mute/unmute
5. Query current program info such as:
	- TV station active, 
    - Programme Name & Description
    - Picon (channel icon) for the station

## How does it work?

![Home Assistant Enigma2 Architecture]({{site.baseurl}}/img/posts/enigma2-hass.png)

To start, I originally developed a python pip module, called [openwebif.py][2], which interfaces with the REST APIs built into OpenWebIf. OpenWebIf is the web interface typically installed on all Enigma2 based receivers. By building a pip module, it removes the need to have all the REST API logic in Home Assistant, and leaves the pip module to handle those details. So if the HTTP API changes some day, the pip module can be updated without having to update the component in Home Assistant.

I then developed a custom **media_player** component for Home Assistant, which allows basic control of the unit and the TV. 


![Home Assistant Enigma2 Preview]({{site.baseurl}}/img/posts/enigma2gif.gif)

You can find the source for the component [on github][3]. 

To install the component, place the file `enigma2.py` inside a folder named  `custom_components/media_player` which is inside your Home Assistant configuration directory.

Then, in your `configuration.yaml` file, add a new entry like this:
```yaml
media_player:
   - platform: enigma2
     host: 10.10.10.4
     name: Vu Duo2
     icon: mdi:satellite-variant
```

Now that it is configured, you can add some automations around this. For example, I have one which turns off the TV when everyone leaves home.

```yaml
######################################################################
##  When everyone has left the house
##    - turn off e2 box and TV
######################################################################

- alias: Standby When Left Home
  trigger:
    - platform: state
      entity_id: group.family
      from: 'home'
      to: 'not_home'

  action:
    - service: media_player.turn_off
      entity_id: media_player.vu_duo2
    - service: ifttt.trigger
      data: {"event":"device_status", "value1":"Home Assistant", "value2":"Everyone Away From Home Triggered"}
```
You could also set one to turn on a light when you turn on the TV, and vice versa:

```yaml
###################################
## Turn living room switch on when Vu comes on, and off when off.
###################################

- alias: Turn lights on when TV comes on
  hide_entity: False
  trigger:
    platform: state
    entity_id: media_player.Vu_Duo2
    from: 'off'
    to: 'on'

  action:
      service: homeassistant.turn_on
      entity_id: switch.living_room_lamp

- alias: Turn lights off when TV goes to standby
  hide_entity: False
  trigger:
    platform: state
    entity_id: media_player.Vu_Duo2
    from: 'on'
    to: 'off'

  action:
      service: homeassistant.turn_off
      entity_id: switch.living_room_lamp
```

## Wrap Up
I hope you find this component useful. I'll be looking to push this into the main Home Assistant repo soon. 


[1]: https://home-assistant.io
[2]: https://github.com/fbradyirl/openwebif.py
[3]: https://github.com/fbradyirl/home_assistant_custom_components
