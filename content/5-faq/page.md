---
Title: FAQ
TitleContent: Frequently Asked Questions
---

## FAQ

### Which platforms are supported?

You probably know, Cocoa runs on macOS. GNUstep using libobjc2 (I call it gnustep-ngr) runs on [BSD](http://wiki.gnustep.org/index.php/Platform:BSD) and [Linux](http://wiki.gnustep.org/index.php/Platform:Linux) (look at [these scripts](https://github.com/plaurent/gnustep-build) if you want to build manually for Debian and Ubuntu. There are no ready-to-go package repositories for Debian/Ubuntu yet). There is work undergoing to make GNUstep with libobjc2 available for Windows as well.

The old Objective C runtime by GCC will run on more platforms including Windows, yes. But keep in mind you then are limited to a language feature set comparable to Objective C 2.0 by the time of Mac OS X 10.5.


### But doesn't look GNUstep old and square and grey?

Well, yes, that's the default look and feel shipped by many Linux distributions. But that's not the whole picture. Just look at [this](https://github.com/BertrandDekoninck/rik.theme/blob/master/newscreen.png) or [this](/dei) (remember: GNUstep **is not** WindowMaker).


### The GNUstep project is dead, isn't it?

I think it always has been a small project with few people working on it. This has not changed. But even though the interest into a Objective C based Free Software project may have ceased a little with the rise of Swift, the GNUstep project is very alive and packages are being maintained, just waiting for more people to come and bring them into shape. This applies even more for GNUstep apps.


### What about ARM?

Manjaro is great at delivering ARM builds. But the openSUSE build service currently does not provide any ARM builds for Arch Linux. So this is planned, but will take some time.


### Reminds me of "Make a Linux app"?

This site of course is inspired by [makealinux.app](https://makealinux.app/). "Stop making Linux distributions, make applications instead." True. But, well. Using GNUstep you will create apps which target more than just Linux. So it deserved its own page. Have fun developing!
