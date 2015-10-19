---
title: Accessing Cocoa Frameworks from Java
author: fin
layout: post
permalink: /2010/03/accessing-cocoa-frameworks-from-java/
onswipe_thumb:
  - http://72.249.5.151/~cp21476/finbarrbrady.com/wp-content/uploads/2010/03/greenshot_2010-03-18_16-06-50.png
category: tech
tags: [ 'tech', 'wp' ]
---
For a long time, I searched for a way to access the Mac OS X Address Book framework from Java. This can be easily done by importing a few of the com.apple Java libraries, however, this will break the cross platform nature of your code as those libraries are not available on Windows and Linux platforms.

Recently I stumbled upon an alternative solution.

Enter, the &#8216;[Rococoa][1]&#8216; framework, which magically uses JNI to allow access to underlying Cocoa libraries.

Rococoa is a generic Java binding to the Mac Objective-C object system. It allows the creation and use of Objective-C objects in Java, and the implementation of Objective-C interfaces in Java.

For example, for class ABPerson, we can simply create the following Java class:

<p style="text-align: center;">
  <img class="aligncenter size-full wp-image-21" title="ABPerson Java" src="http://finbarrbrady.com/wp-content/uploads/2010/03/greenshot_2010-03-18_15-53-53.png" alt="" width="576" height="295" />
</p>

You can see from above, any methods that I need from this class are declared as public abstract methods.

Do the same for class ABAddressBook. Now we can start to access contacts!

First we load the native library &#8216;AddressBook&#8217;

<p style="padding-left: 30px;">
  <img class="size-full wp-image-26 alignnone" title="Load native Lib" src="http://finbarrbrady.com/wp-content/uploads/2010/03/greenshot_2010-03-18_16-06-50.png" alt="" width="445" height="90" />
</p>

Then we get a handle on the Address Book shared instance, and end up with an array of people objects.

<p style="padding-left: 30px;">
  <img class="size-full wp-image-22 alignnone" title="Get the shared address Book" src="http://finbarrbrady.com/wp-content/uploads/2010/03/greenshot_2010-03-18_16-00-05.png" alt="" width="493" height="32" />
</p>

Now we loop through all the contacts

<p style="padding-left: 30px;">
  <img class="size-full wp-image-23 alignnone" title="Loop" src="http://finbarrbrady.com/wp-content/uploads/2010/03/greenshot_2010-03-18_16-00-29.png" alt="" width="382" height="32" />
</p>

Cast the ABPerson object

<p style="padding-left: 30px;">
  <img class="size-full wp-image-24 alignnone" title="Get ABPerson be casting" src="http://finbarrbrady.com/wp-content/uploads/2010/03/greenshot_2010-03-18_16-00-37.png" alt="" width="447" height="26" />
</p>

Now we can get the properties of the record!

<p style="padding-left: 30px;">
  <img class="size-full wp-image-25 alignnone" title="Print person names" src="http://finbarrbrady.com/wp-content/uploads/2010/03/greenshot_2010-03-18_16-00-46.png" alt="" width="403" height="199" />
</p>

Overall, this fantastic tool gives allows Java developers to access virtually anything that you can access from a native Objective-C XCode project. And although it may not be the most elegant solution, it works quite well for most of us!

Let me know what you think in the comments below.

Cheers,

Finbarr

 [1]: https://rococoa.dev.java.net/
