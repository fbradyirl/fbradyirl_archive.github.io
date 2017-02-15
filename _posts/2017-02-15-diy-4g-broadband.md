---
published: false
---
# DIY "Upgrade" Your Home Internet Connection to LTE

Over the past year or so, I have talked to a number of people, who are struggling with their home 'broadband' setup. Everyone has tried a wired connection, be it fibre, DSL or cable. However, if are not in an area covered by Virgin _(formally UPC)_ cable or if you are more than a kilometer or two from your nearest exchange or green cabinet, then you are realistically only to get a trickle of the speeds promosed by the Irish telcos in their drive to push 'fibre' speeds. 

I was also in this same position when I moved into my home a couple of years back. I tried fixed line (with Vodafone) at first. Then WiMax (with AirWire), but in the end, I settled on 4G LTE. But how did I set that up? Read on...

## Hardware
First, you will need one of these two options:
1. a router with a built in LTE modem (and SIM card slot) OR
2. an older "dumb" router which can support an LTE dongle modem, plugged into the USB slot of the router.

Lets take a closer look at both options...

### 1. Easy option: Router with a built in LTE modem

There are several LTE routers out there, but one I have heard good things about is this [TP-Link one on Amazon](http://www.amazon.co.uk/dp/B016ZWXYXG/ref=cm_sw_r_tw_dp_x_imiPybQ6E4TDW). That TP-Link router is a pretty standard, carrier unlocked, router which also gives you wireless N connectivity to the devices in your home. It also is **extensible** in that it has external antennas on the back, which is good, so you have the option to pop in your own at a later stage _(we will discuss this later on...)_.

### 2. "Dumb" router which has a USB slot

So lets talk about a common case, where you might have one or more old routers lying around gathering dust at home. For example, your old Vodafone DSL router (Huawei HG556a). Did you know that you could reflash that router with an open-source firmware, such as [OpenWRT](https://www.openwrt.org), and turn it into a pretty powerful 4G capable device. Even if you don't have one, you can get them [on eBay](http://www.ebay.ie/sch/i.html?_from=R40&_trksid=p2050601.m570.l1313.TR0.TRC0.H0.XHuawei+HG556a.TRS0&_nkw=Huawei+HG556a&_sacat=0) for less than €20.

There are a number of routers you can fit into this category, and the hardware list is [detailed here on the ofmodemsandmen website](http://www.ofmodemsandmen.com/supported.html). That site contains a special modified build of OpenWRT, called **ROOter**, which includes the needed drivers and built in scripts to support plugging in a USB modem and connecting automatically to your 4G network. The main guys who develop the firmware are a friendly bunch of farmers in Australia (I shit you not). They have done a great job of adding an extra 'Modem' section to the standard OpenWRT web UI, and this lets you configure things like the APN, check signal strength and send / recieve SMS messages.

> Ok I have the router, with the ROOter firmware installed, but what about the modem?

So all that is missing now is your modem. One that I can recommend is the [Huawei e3372](https://www.aliexpress.com/wholesale?catId=0&initiative_id=SB_20170215092702&SearchText=huawei+lte+e3372) which goes for about €35 on AliExpress.

