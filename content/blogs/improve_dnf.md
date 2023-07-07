---
author: "Mario Chavez"
title: "Things to do after installing Fedora"
description: "Some tips I consider useful to improve your experience using Fedora Linux"
date: 2023-07-06
image: /images/blogs/improve_dnf/fedora32.jpg
draft: false
tags:
    - fedora
    - development
    - linux
    - dnf
toc:
---

So you just finished installing Fedora on your system, I'm going to tell you about some useful things that you maybe want to do to improve your experience using fedora.

## Configure DNF

As you know **DNF** is the package manager for fedora, but as it comes is kinda slow so I recommend you to add the following lines to improve the speed of installations and updates.

Ad the next lines to `/etc/dnf/dnf.conf` (You will need root permissions to edit this file)

```conf
# See `man dnf.conf` for defaults and possible options

# makes dnf to use the fastest mirror repository
fastestmirror=True
# by default is 3 but you can configure it based in yor internet speed
max_parallel_downloads=10
# on dnf the default option is no so if you press enter the installation will be canceled
defaultyes=True
```

Then may be you want to update your system `sudo dnf update`

## Non-free software

### rpmfusion

During the set up of Fedora just after installing the assistant asks you if you want to allow non-free software, that means that proprietary software can be installed on your system. If you allow it jump to the next point.

If you don't know non-free software include important packages like nivida drivers, nouveau drivers works but not as good, thats only one example there are many more such as obs, ffmpeg, steam, etc.

To add rpmfussion run the next command:

```bash
sudo dnf install https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm

# if you want to install software using the Gnome Software/KDE Discover run the next line
sudo dnf groupupdate core
```

For more information consult [rpmfusion.org](https://rpmfusion.org/Configuration#Command_Line_Setup_using_rpm)

## flathub

[Flathub](https://flathub.org/about) is repository for [flatpaks](https://flatpak.org/about/) is usful for install things that aren't in **rpmfusion** like spotify, the newest version of libre office, discord, etc.

To add flathub run the next line:

```bash
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

More information on [flatpak.org](https://flatpak.org/setup/Fedora)

## Install codecs

Finally what happens to me was that when I installed discord some fonts doesn't render at all what I fond that fix the problem is installing multimedia codecs. I just run the following commands from [rpmfusion.org/Howto/Multimedia](rpmfusion.org/Howto/Multimedia):

```bash
sudo dnf groupupdate multimedia --setop="install_weak_deps=False" --exclude=PackageKit-gstreamer-plugin

sudo dnf groupupdate sound-and-video
```

Thats it, thats the things that improve my expirence on Fedora, hope that helps you.
