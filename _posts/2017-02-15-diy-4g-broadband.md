---
layout: post
published: true
title: DIY "Upgrade" Your Home Internet to LTE
tags:
  - tech
  - iot
  - home automation
subtitle: Sick of your crappy internet? So was I...
---

Over the past year or so, I have talked to a number of people, who are struggling with their home 'broadband' setup. Everyone has tried a wired connection, be it fibre, DSL or cable. However, if are not in an area covered by Virgin _(formally UPC)_ cable or if you are more than a kilometer or two from your nearest exchange or green cabinet, then you are realistically only going to get a trickle of the speeds promosed by the Irish telcos in their drive to push 'fibre' speeds. 

I was also in this same position when I moved into my home a couple of years back. I tried fixed line (with Vodafone) at first. Then WiMax (with AirWire), but in the end, I settled on 4G LTE. But how did I set that up? Read on...

## Hardware
![LTE DIY Home Internet]({{site.baseurl}}/img/posts/lte_home.png)


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

So all that is missing now is your modem (which you can pop a SIM card into). One that I can recommend is the [Huawei e3372](https://www.aliexpress.com/wholesale?catId=0&initiative_id=SB_20170215092702&SearchText=huawei+lte+e3372) which goes for about €35 on AliExpress. 

Once you have the router and modem sorted, you are almost good to go. All you need now is a SIM card from one of the mobile networks. I would advise that you try out SIM cards from different networks to see which one gives the best signal & speeds in your area. 

Personally, I myself went with Three. And, instead of choosing a broadband SIM, I got a [pre-paid SIM card](http://www.three.ie/online/voice/prepay/3pay-trio-sim/) from them. This has the advantage of giving you _unlimited_ data each month when you top up by €20 in one go. Don't worry that it is advertised as a phone SIM. There is no such thing. You are using this for data only and won't be using it for calls or SMS and that is OK. If you went with a Three broadband SIM, you would be limited to a low monthly data cap, plus you can get a nasty bill if you go over your allocation. This is why I would advise against this, and instead go for the pre-pay option.

## Putting it all together

To recap, now you have:
- A router with and integrated SIM slot, or
- A router with OpenWRT (ROOter build) and a 4G dongle plugged into the USB slot.
- and you have a SIM card from your mobile provider.

Now, you have all the hardware ready, just go ahead and top up your SIM card with €20 if you haven't already done so. 

Once you put it all together, you should be able to turn on the router and start surfing the web. Keep an eye on your signal strength and move the router to the best place in your home where you get the best signal. For me, that is in the attic.

### One more thing

The last, but not least, thing I recommend, is that you purchase an outdoor antenna. LTE 4G antennas are pretty cheap and you can pick one up for around €50 online. I can recommend [ATC Supplies](http://www.atcsupplies.ie/search.php?search_for=lte+aerial&manufacturer=*&category=*) who are based in Cavan, but will deliver nationwide. Give them a call and they can advise of the best antenna you can buy to fit the router/modem you are using.

For me, the difference between using an external antenna and not, is the difference between zero percent (yes 0%) coverage, to about ~70% coverage. It makes a huge difference in my home. I believe this is because Three operate on a high freqency and that does not penetrate the walls in my house very well. The external antenna fixes all that as I have it hanging out the window.

Again, play around with the positioning of the antenna until you get the best signal possible.

Good luck with it! You can always give me a shout [on Twitter](https://twitter.com/finbarrbrady) or below in the comments, if you have any questions.
