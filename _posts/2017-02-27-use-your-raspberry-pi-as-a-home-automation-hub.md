---
layout: post
published: false
title: Use Your Raspberry Pi As A Home Automation Hub
---
## Intro

In this article, I will attempt to explain my home automation setup by going step-by-step through the various components.

When deciding on which system to use, my requirements were that my setup be:
1. Secure
2. Private (all data stored locally, within the home)
3. Low(ish) cost
4. Open-Source where possible

There are so many options out there, and I must admit, that I didn't really investigate many in any real depth. [Samsung SmartThings][2] is one of these, but I saw that as a rather expensive option. Something more open, like [OpenHAB][3], was more appealing to me. OpenHAB is built in Java, and has a large user base, but what I settled on proved to suit my needs very well.

## Home Assistant

When I found [Home Assistant][1], I could see that it was a Python project, with a lot of positive momentum, decent documentation, and a good community vibe around it. The fact that it is written in Python appealed to me, as I have Python coding experience, so I felt I could contribute back to it easier than some others. Also, it is very lightweight, and can run easily on a low powered pc or Raspberry Pi. Since I already had a Raspberry Pi gathering dust, I decided to give it a try.

### Installation
Installing Home Assistant is as easy as [a few commands][4]. The team has even built a custom Raspberry Pi OS called Hassbian, which is Raspbian with Home Assistant pre-bundled.

### Configuration & Automations
When you get it installed, you will want to configure it. It has a handy discovery mechanism, which takes a couple of minutes to auto-discover supported devices in your LAN. You will be surprised how many devices it will find. For example, last week, it detected my Apple TVs, with zero config from me!

In the rest of this article, I will run through some examples of my configuration and automations around the devices.

#### Device Tracking

To start off, I wanted to have some kind of device tracking, to know when the house is occupied. You can use motion sensors for this, or do like I did, and hook into your home router. 

In my case, I am using OpenWRT on my router, and Home Assistant is able to query it for associated devices on the network. The idea here, is that when you leave the house, you leave the wifi network and you get dropped from the route `arp` table after a few minutes.

Here is my config to add the router.

```yaml
- platform: luci
  host: !secret router_ip
  username: !secret router_username
  password: !secret router_password
  interval_seconds: 45
```

You will notice I have the values as `secret`. This is handy if you want to share your config, but keep sensitive data private. To support this, create a file called `secrets.yaml` under the root of your configuration folder, and add entries to it as follows:

```yaml
router_ip: 192.168.1.1
router_username: admin
router_password: mypassword123
```

[1]: http://home-assistant.io
[2]: https://www.smartthings.com
[3]: http://www.openhab.org
[4]: https://home-assistant.io/getting-started/