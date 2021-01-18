---
Title: IDE
TitleContent: Integrated Development Environment
---

You can almost always build any GNUstep app project with a terminal procedure like this:

```
. /usr/GNUstep/System/Library/Makefiles/GNUstep.sh 
[./configure]
make [-j4]
[sudo -E make install]
```

The first line includes all the environment variables needed for GNUstep make to build an app, the second (optional) will configure the build process if needed, the third will start the actual build process (`-j` specifies the number of concurrent builds, should be the number of your CPU cores). `make install` will install the build result into `/usr/GNUstep/Local`. Remember to always use `-E` as this preserves the environment variables set by `GNUstep.sh` and necessary for GNUstep `make`.

## Develop graphical user interfaces

Coming from macOS you probably know Xcode was divided into Interface Builder and Xcode / Project Builder in earlier times. The "Interface Builder" of GNUstep is "Gorm.app". It is the central tool for creating graphical user interface leveraging gnustep-gui (AppKit framework). Just set your desktop environment to open `.gorm` files using Gorm.app (`/usr/GNUstep/System/Tools/Gorm`). You are then ready to go to use Gorm:

[image gorm-app.png "Screenshot showing Gorm.app editing a SystemPreferences Panel"]

For more information on how to do this see [further documentation](/credits) regarding GNUstep and Cocoa development.

### Different approaches for building cross platform GUI

Basically you may choose one of the following paths if you plan to compile your app on macOS as well:

1. Create the interface using Gorm (and `.gorm` files) and export `.nib` files. Cocoa will probably be able to read and execute these `.nib` files, but you probably *will not* be able to edit them using Xcode.
2. Create the interface using Xcode (and `.xib`files) and use these for GNUstep. gnustep-gui (GNUstep AppKit framework) *will* probably be able to read and execute this `.xib` (as long as you use only classes and technologies which exist within GNUstep), but you currently *will not* be able to edit these files using Gorm.
3. Create and edit `.gorm` files and `.xib` files and use both with the same Objective C code. These files can peacefully coexist as GNUstep chooses to load `.gorm` files over existing `.xib` files.

## Edit code

[KDevelop](https://www.kdevelop.org/) (based on [Kate](https://kate-editor.org/)) is a very advanced and complete free (as in "free speech") Integrated Desktop Environment (IDE) leveraging the power of clang. It is primarily optimized for editing C++ code, but it supports GNUmakefiles and due to the capabilities of clang it will work with Objective C(++) quite well.

Using Arch/Manjaro just install KDevelop using `sudo pacman -S kdevelop` and open an project by directing KDevelop to the project's GNUmakefile.

After opening an GNUstep app project, adjust its settings by adding and setting the required includes, which should be at least `/usr/GNUstep/System/Library/Headers`:

[image kdevelop-define-includes.png "Settings dialogue of KDevelop, showing the configured includes"]

Open the general settings of KDevelop and set "Clang format" as source code formatter to get that feature for Objective C as well. Just add a `.clang-format` file to your project. I recommend the ["NYTimes Objective-C Style Guide"](https://github.com/nytimes/objective-c-style-guide), which is represented by [this clang-format file](https://github.com/MariusCiocanel/clang-format).

You then are able to start editing your code. KDevelop will provide you [common features like syntax highlighting, code formatting, code completion and quick code navigation](https://www.kdevelop.org/features):

[image kdevelop-editing.png "Screenshot of KDevelop showing Objective C code and the code completion feature"]

## Start building from KDevelop

KDevelop offers direct access to a terminal which you can use to build your projects. If you wish to use the GUI button, save a wrapper script like this one to a place you like and set this as your project's `make` executable:

```
#!/bin/bash
. /usr/GNUstep/System/Library/Makefiles/GNUstep.sh 
make "$@"
```
