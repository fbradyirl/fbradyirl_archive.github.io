---
title: Stripping PowerPC parts from your Mac app
author: fin
layout: post
permalink: /2011/04/stripping-ppc-parts-from-mac-apps/
featured_img:
  - http://finbarr.dev/wp-content/uploads/2011/04/stevex64.jpeg
onswipe_thumb:
  - 'http://finbarr.dev/wp-content/plugins/onswipe/thumb/thumb.php?src=http://finbarr.dev/wp-content/uploads/2011/04/stevex64.jpeg&amp;w=600&amp;h=800&amp;zc=1&amp;q=75&amp;f=0'
category: tech
tags: [ 'tech', 'wp' ]
---
<img class="alignright size-full wp-image-667" title="stevex64" src="http://finbarr.dev/wp-content/uploads/2011/04/stevex64.jpeg" alt="" width="264" height="175" />If you are a developer with an app in the Mac App Store, then you have probably come across this Apple rule:

> Application executables may support either or both of the Intel architectures:
>
> i386 (32-bit)
> x86_64 (64-bit)
>
> Other architectures may not be included in submitted binaries.

No problem says you. However, until recently, Apple did not check things like dylibs contained within your app bundle. They do now.

This means that you must make sure that any 3rd party components you have imported to your project are stripped of any old PPC remnants or they will fail validation and be rejected within 5 minutes of submission (seems like they have automated these checks).

So how do we do this? Simple enough, but it requires and extra step after building the archive.

  1. First to be safe, you should check your target build settings to ensure that your target architectures are set to i386 and x86_64.  So first click on the Project in XCode, then select the target:
    <img class="aligncenter size-full wp-image-644" title="Select target" src="http://finbarr.dev/wp-content/uploads/2011/04/Screen-shot-2011-04-27-at-21.55.21.png" alt="" width="442" height="55" /> Then, under the &#8216;Build Settings&#8217; tab look at the &#8216;Valid Architectures&#8217; and check that it looks like this:<img class="aligncenter size-full wp-image-645" title="Arch" src="http://finbarr.dev/wp-content/uploads/2011/04/Screen-shot-2011-04-27-at-22.08.30.png" alt="" width="402" height="175" />
  2. Then, as normal, build the product for Archive<img class="aligncenter size-full wp-image-646" title="Screen shot 2011-04-27 at 22.10.08" src="http://finbarr.dev/wp-content/uploads/2011/04/Screen-shot-2011-04-27-at-22.10.08.png" alt="" width="272" height="128" />
  3. The Organser window should open automatically when done. At this point, we&#8217;re interested in finding the .app bundle. Where is it? Lets see&#8230; Right click on the archive, and select &#8216;Show In Finder&#8217;<img class="aligncenter size-full wp-image-647" title="Screen shot 2011-04-27 at 22.12.25" src="http://finbarr.dev/wp-content/uploads/2011/04/Screen-shot-2011-04-27-at-22.12.25.png" alt="" width="497" height="134" />
  4. The xcarchive location will be shown. Right click and &#8216;Show Package Contents&#8217;<img class="aligncenter size-full wp-image-648" title="Screen shot 2011-04-27 at 22.13.59" src="http://finbarr.dev/wp-content/uploads/2011/04/Screen-shot-2011-04-27-at-22.13.59.png" alt="" width="392" height="114" />
  5. Inside here, browse to Products/Users/NAME/Applications/ to see your .app bundle<img class="aligncenter size-full wp-image-649" title="Screen shot 2011-04-27 at 22.17.25" src="http://finbarr.dev/wp-content/uploads/2011/04/Screen-shot-2011-04-27-at-22.17.25.png" alt="" width="411" height="165" />This is the .app bundle we need to strip non x86 or 64 parts from before signing and submitting to Apple. To do this we can use something like [TrimTheFat][1], by dragging the .app bundle into it&#8217;s window and deleting the resulting Jelly SMS Lite-U.app (as it&#8217;s not needed any more).Or alternatively, we can run the following command on the .app bundle.

<pre>ditto --rsrc  --arch i386 --arch x86_64 MyApp.app build/MyApp.app</pre>

(from [Apple Dev Forums][2])

If anyone knows of a way this command can be automatically run during the archive or build process (possibly during a build step maybe??), please let us know in the comments below&#8230;

**<span style="color: #ff0000;">[Update]</span> Important**: *I forgot to mention &#8211; you should launch your .app at this stage to test if you&#8217;ve actually stripped out something that your app depends on. If so, you will get a crash here. In this case you will need to look at your project more closely and remove the code/parts causing the exceptions.*

Now you can simply submit your archive as before and the nasty stuff should all be gone from it and you will once again be in Apple&#8217;s good books.

 [1]: http://homepage.mac.com/gweston/macware/TrimTheFat.zip "Trim The Fat"
 [2]: https://devforums.apple.com/message/418977#418977
