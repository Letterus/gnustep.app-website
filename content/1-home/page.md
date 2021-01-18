---
Title: Start
TitleContent: Make a GNUstep app!
---

[image gnustep-apps.png "GWorkspace showing a directory with several GNUstep apps"]

Developers coming from macOS and Cocoa programming – or liking Objective C as a programming language – might want to create great cross-platform apps. Or might want to create Objective C(++) apps, which run on a free (as in free speech) environment using Free Software.

They want to use modern language features of Objective C and are used to a development environment which is up and usables in minutes.

This is perfectly possible using [GNUstep](http://http://gnustep.org/]) and its [libobjc2 runtime](https://github.com/gnustep/libobjc2) which provide modern language features leveraging clang, such as Automatic Reference Counting (ARC), blocks (closures) and synthesis of declared properties known from OS X 10.7 (Lion) and later.

It's just it took me more than a year to find out how this can be put together and delivered to users. Therefore I created this page. It will help you to get up and running within minutes.

Have fun and of course you're welcome to leave your feedback to improve information documented here!


## Install and getting started

For using the packages I compiled together for this setup you currently need an [Arch](https://archlinux.org/) based Linux distribution like [Manjaro](https://manjaro.org/).

### Install packages from [repository](https://build.opensuse.org/project/show/home:letterus:gnustep-ngr) via pacman

Add the following lines to your ```/etc/pacman.conf``` with ```sudo nano /etc/pacman.conf```:

```
[home_letterus_gnustep-ngr_Arch]
SigLevel = Optional TrustAll
Server = https://download.opensuse.org/repositories/home:/letterus:/gnustep-ngr/Arch/$arch
```

Install the basic package groups:

```
sudo pacman -Syy gnustep-ngr gnustep-ngr-dev gnustep-ngr-desktop
```

If you use Manjaro it is possible you need to [switch to the testing or unstable branch](https://wiki.manjaro.org/index.php?title=Switching_Branches) as that repo is built against Arch packages/dependencies. Currently you need **testing**.

### Direct download (manual installation)

https://download.opensuse.org/repositories/home:/letterus:/gnustep-ngr/Arch/x86_64/


### Getting started

The commands above will install all the GNUstep packages you need. Proceed further with:

1. [Integrate GNUstep into your desktop environment (DEI).](/dei)
2. [Run an integrated development environment (IDE)](/ide)

## Strategy

Currently I target at users of Arch based Linux distributions like Manjaro. Desktop app developers often like using such distributions, because they are very up to date. I ship packages which are built from the latest (GNUstep) sources to enable developers to use the newest features and fixes available.

Once there are updates and releases of apps we created, I have plans to create stable packages for openSUSE. [Builds](https://build.opensuse.org/project/show/home:letterus:gnustep-ngr) are using [openSUSE's build service](https://build.opensuse.org/).


## Continous Delivery

If you've got a working state of your application, just [point me](/contact) to your git/svn repository. I'll happily provide you and your users a package and an API key which enables automatic builds on commit/push from your repository.
