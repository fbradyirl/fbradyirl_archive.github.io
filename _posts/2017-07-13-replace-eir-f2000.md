---
layout: post
published: true
title: Using Your Own Router for Eir eFibre
date: '2017-07-13'
tags:
  - >-
    eFibre - Eir - Eircom - FTTH - OpenWRT - LEDE - 3rd Party Router - PPPoe -
    IPoE - Huawei - F2000 - HG659b
subtitle: >-
  Having wifi issues with your Huawei F2000? Might be time to look for an
  alternative...
---
## Replacing the Eir F2000 Router

Recently, I was lucky enough to get Fibre To The Home (FTTH) connected at my abode, and was kindly provided a wireless router from Eir. It is the Huawei F2000 (HG659b). The F2000 is reported to have _lots_ of issues with wifi, so you might look to replace it with something else, right? Yes. Good idea.

The F2000 user guide states:

> The eir F2000 eir Fibre Modem is a next generation voice gateway that supports very-high-data-rate digital subscriber line 2 (VDSL2) uplink, one Giga Ethernet uplink port and 4 Giga Ethernet downlink ports. 

That all sounds great, however the VDSL2 part is overkill for FTTH. All that is connected to it is a single ethernet cable from the Eir installed Optical Network Terminal (ONT). It is the one on the left here:

![]({{site.baseurl}}/img/eirinstalled.jpg)

That yellow cable just plugs into the WAN port of the F2000. So this is basically just IP over Ethernet. This means you can use any router you like instead of the F2000. No DSL/VDSL modem required. No PPPoe or other acronym crunching protocol needed. Just a bog standard Ethernet cable and a router which supports negiotating an IP address via DHCP (AKA every router made ever). It also needs to support setting the wan to recieve and transmit on a VLAN. Not all default firmwares will allow this, but all the major opensource ones do, such as OpenWRT/DD-WRT/Tomato. 

So, for me, I happen to have a [Linksys E4200v2](https://wiki.openwrt.org/toh/linksys/ea4500) which I flashed [OpenWRT/LEDE](http://lede-project.org) onto. I already had this setup with various bits and pieces I want. To connect the new fibre internet to it was simple (once I found out how!).

Basically you just need two things:
1. Set the WAN connection to be a DHCP client
2. set the VLAN (802.1q) tag to 10

In OpenWRT/LEDE all you need to do to make this happen is the following. Edit `/etc/config/network` as follows:

```
config switch_vlan
	option device 'switch0'
	option vlan '10'
    # port 4 is the wan port on my router 
    #  ... (this could be different for yours)
	# 6 stands for the eth1 interface
	option ports '4t 6'

config interface 'wan'
	option proto 'dhcp'
	option ifname 'eth1'
```

And restart. That's it! You will see now that your wan interface will pick up a public IP address. Now throw that F2000 in the cupboard. 

