---
title: Building for Multiple Targets in XCode
author: fin
layout: post
permalink: /2010/03/building-for-multiple-targets-in-xcode/
featured_img:
  - /images/Targets.png
onswipe_thumb:
  - 'http://finbarrbrady.com/wp-content/plugins/onswipe/thumb/thumb.php?src=http://finbarrbrady.com/wp-content/uploads/2010/03/Screen-shot-2010-03-18-at-23.38.12.png&amp;w=600&amp;h=800&amp;zc=1&amp;q=75&amp;f=0'
categories:
  - iPhone Development
tags:
  - Application Template
  - C Flag
  - Demo Project
  - Direction
  - Flags
  - Free Version
  - homepost
  - Iphone
  - Long Time
  - Meaningful Name
  - Meaningful Names
  - New Flag
  - Nightmare
  - Plunge
  - Purchasing
  - Target
  - Targets
  - Utility Application
---
Some months ago, I needed to create new versions of my app&#8217;s. I wanted to do this without duplicating any code or projects. <!--more-->So I did some research and decided to figure out how to build towards multiple targets in XCode.

<img class="aligncenter" title="Targets" src="/images/Targets.png" alt="" width="625" height="236" />

This is something I shied away from for a long time as I thought it would be a nightmare to figure out. What I discovered was that it&#8217;s much easier than I first thought, and also much more powerful as well.

So why do I need to do this? There are a few reasons:

  * To create different versions of your app which have different features. E.g. a &#8216;Lite&#8217; or &#8216;Free&#8217; version
  * To create targets which are tailored for different devices, possible with the same model and controller classes, but different view classes E.g. one target for iPhone, and another for iPad

So how do we do it?

Lets create a simple demo project.

In XCode, create a new project based on the &#8216;Utility Application&#8217; template. Lets call it &#8216;TargetTest&#8217;.

Click on &#8216;Build and Run&#8217;

<img class="aligncenter size-full wp-image-61" title="Target1" src="http://finbarrbrady.com/wp-content/uploads/2010/03/Screen-shot-2010-03-18-at-23.12.24.png" alt="" width="121" height="37" />

Notice under &#8216;Targets&#8217; that there is one default target called &#8216;TargetTest&#8217;

We can create a new target by simply duplicating this one. Right click on that target and select &#8216;Duplicate&#8217;

<p style="text-align: center;">
  <img class="size-full wp-image-63 aligncenter" title="Duplicate Targets" src="http://finbarrbrady.com/wp-content/uploads/2010/03/Screen-shot-2010-03-18-at-23.15.15.png" alt="" width="148" height="113" />
</p>

<p style="text-align: left;">
  You will notice a new info.plist copy is made for this new target. We can add target specific information here, such as changing the &#8216;Bundle Display Name&#8217;.
</p>

<p style="text-align: left;">
  Lets rename the newly created target, TargetTest_VIP
</p>

<p style="text-align: left;">
  <img class="aligncenter size-full wp-image-65" title="Rename Target" src="http://finbarrbrady.com/wp-content/uploads/2010/03/Screen-shot-2010-03-18-at-23.24.17.png" alt="" width="148" height="55" />
</p>

<p style="text-align: left;">
  Now, right click on the new target, and select &#8216;Get Info&#8217;. Under the &#8216;Build&#8217; tab, ensure you have Configuration set to &#8216;All Configurations&#8217;.
</p>

<p style="text-align: left;">
  Now we want to add a new flag under the &#8216;Other C Flags&#8217; setting. We will enter -DVIPVERSION
</p>

<p style="text-align: center;">
  <img class="size-full wp-image-66 aligncenter" title="Other C Flags" src="http://finbarrbrady.com/wp-content/uploads/2010/03/Screen-shot-2010-03-18-at-23.27.27.png" alt="" width="394" height="240" />
</p>

<p style="text-align: left;">
  We should also at this point, change the Product Name to a more meaningful name as shown.
</p>

<p style="text-align: left;">
  <img class="aligncenter size-full wp-image-67" title="Target Name" src="http://finbarrbrady.com/wp-content/uploads/2010/03/Screen-shot-2010-03-18-at-23.29.31.png" alt="" width="481" height="68" />
</p>

<p style="text-align: left;">
  Now, to see how it works, we will modify MainViewController.m slightly. In the showInfo method, we want to check which target we are running on.
</p>

<p style="text-align: left;">
  <img class="aligncenter size-full wp-image-68" title="Target ifdef" src="http://finbarrbrady.com/wp-content/uploads/2010/03/Screen-shot-2010-03-18-at-23.31.44.png" alt="" width="633" height="338" />
</p>

<p style="text-align: left;">
  So as you can see, if the C flag we defined is detected, the code will run in one direction, if not, then we go another way. We could easily give users who used in-app purchasing more features at this point for example.
</p>

<p style="text-align: left;">
  Now, to test, we simply choose TargetTest_VIP from the Active Target dropdown, and &#8216;Build and Run&#8217;.
</p>

<p style="text-align: left;">
  <img class="aligncenter size-full wp-image-69" title="Active Target" src="http://finbarrbrady.com/wp-content/uploads/2010/03/Screen-shot-2010-03-18-at-23.35.58.png" alt="" width="312" height="83" />
</p>

<p style="text-align: left;">
  Now, when we click on the info button, we get the VIP message:
</p>

<p style="text-align: center;">
  <img class="aligncenter size-full wp-image-70" title="VIP" src="http://finbarrbrady.com/wp-content/uploads/2010/03/Screen-shot-2010-03-18-at-23.38.12.png" alt="" width="265" height="493" />
</p>

<p style="text-align: left;">
  <p style="text-align: left;">
    Now if we run again, but this time first select the Active Target, TargetTest, when we press the info button, the view flips.
  </p>
  
  <p style="text-align: left;">
    You will also notice that 2 separate targets are built in your build output folder.
  </p>
  
  <p style="text-align: left;">
    So overall this makes things a lot easier when it comes to distribution and allows maximum code reuse which can only be a good thing!
  </p>
  
  <p style="text-align: left;">
    Download the demo project <a href="http://finbarrbrady.com/files/demos/TargetTestDemo.zip">here</a>.
  </p>
  
  <p style="text-align: left;">
    If there&#8217;s anything I&#8217;m missing, please leave a comment and I can add it to the post.
  </p>
  
  <p style="text-align: left;">