
<h1 style="font-family: Hacked;
    ">plymouth-watch_dogs-theme</h1>


A simple <span style="font-family: Hacked;
    ">Watch_Dogs</span> theme for plymouth, with encryption unlocking support.

![Animation Step 1](img/animation-0005.png "Animation Example 1 (Moving bars)")
![Animation Step 2](img/animation-0011.png "Animation Example 1 (Boot Sequence text)")
![Animation Step 3](img/animation-0065.png "Animation Example 1 (ctOS Logo)")

The theme is derived from the plymouth two-step spinner default theme and is very dark and simple.

## What is [Plymouth](https://www.freedesktop.org/wiki/Software/Plymouth/)?

> [Plymouth](https://www.freedesktop.org/wiki/Software/Plymouth/) is a project from Fedora and now listed among the [freedesktop.org's official resources](https://www.freedesktop.org/wiki/Software/#graphicsdriverswindowsystemsandsupportinglibraries) providing a flicker-free graphical boot process. [...] [Plymouth] provides an eye-candy splash screen leading all the way up to the login manager. - [Arch Wiki](https://wiki.archlinux.org/index.php/Plymouth) 

Simply: A boot splash screen for Linux.

## Installation



First you got to have your plymouth up and running. On Ubuntu and Fedora this should already be the case after installtion. On Arch and other distributions, help yourself. ;) 

After that you can install this theme and the following steps show you how:

1) Download or clone this repository and its contents.

    Use the big green button on the top right.

2) Rename the folder to `watch_dogs` and copy it into the plymouth themes directory.

    You might need root access. 

    For me the themes directory was at: `/usr/share/plymouth/themes`

    If it is not called `watch_dogs` when it's inside the plymouth themes directory, it might not work properly.
    
    
    This should be the content of the t

3) Set the theme

    First check if it is there.

    ```sh
    plymouth-set-default-theme --list
    ```

    ```txt
    details
    fade-in
    glow
    script
    solar
    spinfinity
    spinner
    text
    tribar
    watch_dogs <-- Here it is
    ```

    If it isn't showing up, plymouth can't find it or it's config file.

    Then, change it. (But not so hasty, are we?) Because we will need to rebuild the initrd.

    You can set it with:

    ```sh
    plymouth-set-default-theme watch_dogs
    ```

    But this alone will have no effect and it won't show up!

    The initrd needs to be rebuilt for it to take effect. On Ubuntu and Fedora you should be safe to do:

    ```sh
    plymouth-set-default-theme watch_dogs --rebuild-initrd
    ```

    Which will do the work for you.

    I personaly set up a different initramfs for plymouth so I have the option to boot without it. You have to do this manually after changing the theme though. For Arch look at: [Arch Wiki: Mkinitcpio - Image creation and activation](https://wiki.archlinux.org/index.php/Mkinitcpio#Image_creation_and_activation)

    Also check out `plymouth-set-default-theme --help` for further options and instructions


That's it.


<h2 style="font-family: Hacked; src: url(https://hackedfont.com/HACKED.ttf);"> The awesome font</h2>

The Watch_Dogs font I used in this README and this theme is called [Watch_Dogs font](https://watchdogsfont.com) by [David Libeau](https://davidlibeau.fr/)

