---
Title: DEI
TitleContent: Desktop Environment Integration
---

This tutorial shows how to integrate GNUstep apps into your desktop environment easily. You could use any desktop environment that provides a global menu. But as I recommend KDevelop as an [IDE](/ide) for developing GNUstep apps, we are going to use Manjaro Plasma/KDE in this example.

When you're presented with the Manjaro Desktop, add a panel at the top of the screen. It should have 26px of height. You may add KDE widgets as you like. Be sure to add a "Global Menu" widget at the left and a spacer between the menu and supplementary widgets.

[image dei-step-1.png "Create a top panel to your DE"]

You might want to remove, modify and/or hide the panel at the bottom. If you then use an KDE app, it will look like this: 

[image dei-step-3.png]

Then fire up SystemPreferences.app (installed with [the basic gnustep-ngr-desktop installation](/)) and choose "SombreManjaro" as your GNUstep theme (click "Apply" and "Save"):

[image dei-step-4.png "Choosing SombreManjaro using SystemPreferences"]

SystemPreferences.app is going to look like this (might need a restart though):

[image dei-step-5.png "SystemPreferences.app using SombreManjaro.theme"]

This setting will apply for all GNUstep apps. This way you achieved an optical integration of GNUstep's horizontal menu in a top panel. This works well, but has the drawback that it will invisibly cover the KDE widgets which are not clickable as long as a GNUstep app is active.

## DBus menu integration

One day you might be able to use the DBus menu integration of GNUstep (this is currently unfinished/buggy). I'll already show you how to use it.

Open the "Defaults" panel of SystemPreferences.app and change `NSMenuInterfaceStyle` from `NSMacintoshInterfaceStyle` to `NSWindows95InterfaceStyle`:

[image dei-step-6.png "Choose a different menu style using SystemPreferences.app"]

 You will not get a Windows 95 style, but an integration of the GNUstep menu into the DBus Global Menu widget from Plasma. If you restart the app it will look like this:

[image dei-step-7.png "SystemPreferences.app using the global DBus Menu widget from Plasma"]

This way all your KDE/Plasma widgets continue to work, but there are some bugs with GNUstep apps currently.

## Proceed

You might want to adjust font/sizes and the modifier keys you want to use. You can do so easily using SystemPreferences.app.

After this you might want to proceed with setting up your [Integrated Development Environment](/ide).
