---
title: Jelly SMS for Mac public beta
author: fin
layout: post
permalink: /2011/01/jelly-sms-for-mac-public-beta/
enclosure:
  - |
    |
        http://www.extraextra.ie/files/JellyMacDemo1.mp4
        497501
        video/mp4

onswipe_thumb:
  - 'http://finbarr.dev/wp-content/plugins/onswipe/thumb/thumb.php?src=http://finbarr.dev/wp-content/uploads/2011/01/512x512.png&amp;w=600&amp;h=800&amp;zc=1&amp;q=75&amp;f=0'
category: tech
tags: [ 'tech', 'wp' ]
---
Update March 7 2011: The beta period is now over. Thanks so much to those who helped out, and reported issues and feedback. Jelly SMS is now available on the Mac App Store. See[ JellySMS.com][1] for more info and to get the app.

<p style="text-align: center;">
  <img class="aligncenter size-full wp-image-600" title="JellyScreen1" src="http://finbarr.dev/wp-content/uploads/2011/01/JellyScreen1.png" alt="" width="477" height="294" />
</p>

<p style="text-align: center;">
  &nbsp;
</p>

** **

** **

** **

[Jelly SMS Mac App Store demo video][2]<img class="alignright size-thumbnail wp-image-628" title="512x512" src="http://finbarr.dev/wp-content/uploads/2011/01/512x512-150x150.png" alt="" width="150" height="150" />

Jelly SMS has been re-designed from the ground up, so why not download this preview and get texting on your Mac! The beta will expire within 2 weeks and is only supported on Mac OS 10.6.6 or later.

***What&#8217;s still missing:***

  * Message History
  * Delivery Reports
  * Many little features that I haven&#8217;t told you about yet
***What&#8217;s fixed in the latest build:***

  * Drag and drop now works from Address Books
  * Background sending so that you can start a new message straight after clicking send.
  * Group sending including to defined [distribution list][3] numbers.
  * State is now fully saved on exit (recipients and message)
Please let me know of any bugs you find or features you&#8217;d like to see. Preferably, please feedback using the Jelly SMS>About>Contact Support menu as this lets me know important information to help me debug your setup.

** **

** **

**<a onclick="javascript: pageTracker._trackPageview('/goal/clickMacBeta.html');" href="http://www.jellysms.com/desktop/">Download from JellySMS.com</a>**

** **

** **

** **

Thanks for all the feedback so far guys. It is hugely appreciated.

## **Faq**

** **

** **

** **

**Why are you releasing a new version of Jelly SMS only for Mac?**

When Apple announced the Mac App Store, they made it clear that applications developed in Java could not be accepted. They also deprecated the latest Apple Java Runtime around the same time, and noted that Java would [no longer be installed by default][4] on new Macs.

This left me with 2 options for Jelly SMS on the Mac:

  1. Continue on as we were and maintain the Java desktop version of Jelly SMS, in the knowledge that our long term user base would be gradually reduced in time with the release of Mac OS 10.7 (Lion) as Java would no longer come pre-installed with new Mac&#8217;s. This extra step of downloading and installing a JRE is not something novice users will do.
  2. Develop a new Cocoa application from scratch, which complies fully with the Mac App Store submission rules. Doing this will enable users to get the app in the most convenient and simplest way, and will remove any confusion about Java, runtimes and all that technical stuff they don&#8217;t care about.

I decided to do both. Keep the existing Java app alive, while building a new version exclusively for the Mac.

Developing from scratch also has a number of other advantages:

  * Using past experiences and lessons learnt from building many versions of the app across Windows, Mac, Linux, iOS and Android, we have developed an extremely efficient operator framework, which allows us to react to any changes on the provider websites (e.g. Vodafone.ie) within **minutes, **without the need to re-compile and re-release a patch to fix any breakages caused. This change alone can save the user weeks of frustration as they wait for Apple to approve a small update.
  * By removing this dependency on Apple&#8217;s approval process, we can add support for new operators in a matter of minutes. All the user has to do is restart the app, and boom, they get the new feature or bug fix **instantly**.
  * Developing in Objective-C means we can make an app that actually *feels* like a proper Mac application, which is tricky to do using Java (especially when targeting for cross-platform).
  * We can take advantage of many of the cool native frameworks available such as Core Animation to enhance the user experience in ways that are not possible without a lot of work in Java.

**Why will the beta version expire?**

The beta will help us identify bugs, and hopefully gain some great feedback from users. In order to prevent users from running an old buggy version, I have time limited the betas. At the end of that period, the user will be prompted to download the latest beta, thus keeping you up to date with the latest fixes.

*Hint: users who provide good feedback stand a great chance of getting a free promo-code for the app when it is released in the Mac App Store.*

**Does this mean that you will no longer be providing the &#8216;free&#8217; Java version of Jelly SMS Desktop for Mac?**

We will continue to offer the Java version of Jelly SMS Desktop for Mac for free alongside it&#8217;s Windows & Linux counterparts. There will be no change here. You can still find the old Java version on the Sourceforge.net [page][5].

However, we will encourage users to use the Mac App Store version as this version will be the simplest to install, provide the best user experience, and as outlined above, will get provider related fixes instantly.

 [1]: http://www.jellysms.com/desktop/
 [2]: http://www.extraextra.ie/files/JellyMacDemo1.mp4
 [3]: http://docs.info.apple.com/article.html?path=AddressBook/4.0/en/ad44.html
 [4]: http://finbarr.dev/2010/10/mac-app-store-users-developers/
 [5]: https://sourceforge.net/projects/jsmsirl/
