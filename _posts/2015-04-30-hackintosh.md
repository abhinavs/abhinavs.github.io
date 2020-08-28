---
layout: post
title: Hackintosh
excerpt: "My five-hour struggle to install Yosemite on an old Lenevo laptop;
some learnings"
tags: [Yosemite, OSX, Hackintosh, Tech, TechNotes]
comments: true
---
For the longest time, I wanted to experiment installing OS X on my laptop. I recently got the chance to
try it out for the first time. Though it took me more than five hours to get it right, but it was worth it.
<br />
<br />
If you are also trying out yourself, follow these steps:

* Follow instructions given on [this page](http://www.tonymacx86.com/yosemite-desktop-guides/143976-unibeast-install-os-x-yosemite-any-supported-intel-based-pc.html#create_unibeast), download Yosemite from AppStore and create a UniBeast enabled bootable USB drive. This process should be pretty simple.
* Using the bootable drive, try installing it on your PC. However, If you are unlucky like me, installation will keep ending abruptly. Don't panic. First suggestion is to boot using -v flag and try finding exact problem.
* In my case, I kept getting `still waiting for root device` error. I tried a lot of things including manually fixing UniBeast drive. Here is the final snapshot of my `Extra/org.chameleon.Boot.plist`
{% gist 85041db0de4bc74798a4 %}
* I also had to update a couple of kext (kernel extension) files present in `Extra/Extensions` directory.
    * [OS X Generic USB3 kext](https://bitbucket.org/RehabMan/os-x-generic-usb3/downloads)
    * [Voodoo PS2 Controller kext](https://bitbucket.org/RehabMan/os-x-voodoo-ps2-controller/downloads)

I still have some trouble setting up my wifi. I have also gotten habitual of retina display and I am missing it dearly. Let me see how long I can work on
this setup before returning to my MacBook Pro.
