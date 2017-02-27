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



[1]: http://home-assistant.io
[2]: https://www.smartthings.com
[3]: http://www.openhab.org