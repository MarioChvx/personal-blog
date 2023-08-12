---
author: "Mario Chavez"
title: "My take on best Linux distributions for beginners"
description: "An article in witch I explain my opinion about some distributions commonly categorized as beginner-friendly and give recommendations based on my experiences."
date: 2023-07-31
image: /images/blogs/beginer-distros/tierlist.png
draft: false
tags:
    - linux
    - debian
    - fedora
    - ubuntu
    - distributions
toc: true
mathjax: false
---

In this article I want to talk with the people that are coming from Windows o MacOS and have the intention to try or switch to Linux, so I only talking about the desktop version of each distribution.

## What are Linux and distributions?

If you are not familiar with Linux let's remember that Linux isn't an operating system, is just the kernel the part of the OS that connects the hardware with the applications but Linux needs some applications to become a fully functional operating system here is when GNU comes into place. Now then when someone says Linux most of the time refers to GNU/Linux where GNU corresponds to a library of software that are FOSS (Free and Open Source Software) and can act as an operating system in union with Linux and basically that was more or less the first distribution of Linux.

Now in the Linux environment a distribution, also called "*distro*" it is a collection of software pre-bundled with the purpose of being convenient to the user. It can include GNU, display managers, window managers, office suites, web browsers and other useful things that we take for granted and didn't even notice.

The great thing about this approach in operating systems is tha you can personalize your system as much as you want or even build your own system. However this freedom comes with the cost of learning how your system really works.

## Best

I think the following are the best distributions that let you enter to the world of Linux, scrap the surface, learn the basics while also have a functional system.

### Linux Mint

Its purpose is to be beautiful, modern and easy to use. It's a fork of Ubuntu so his package manager is *aptitude* thats good because has a lot of documentation. By default, it comes with Cinnamon, a desktop environment that has similar layout  to Windows, comes with a lot of useful GUI that lest you configure your system without using the terminal. My recommendation is to use the GUIs as training wheels and gradually transition to using the terminal more often.

### Nobara Linux

A gaming-oriented distribution, Nobara is developed by Glorious Egg roll a developer know for his contributions and optimizations to Proton, a piece of software that Valve includes with Steam, allowing games written to Windows run o Linux. It is a fork of Fedora, so its package manager is dnf and comes with Gnome desktop environment witch is easy to use but is different from MacOS and Windows. So, you will need a little bit of time to become familiar with it. I must say that most of the games run on Linux; the only ones that definitely do not run are the ones that come with anti-cheat software.

My recommendation is, if you want to play games go with Nobara. While you can also play games on Mint, Nobara has more recent packages and performs better.
Linux Mint is excellent for every day use and stable.

## Good

The following are just as good as the two above the difference is that they are rough in the edges.

### Peppermint OS

His main goals are to provide a functioning system with minimum hassle. While allowing the user to personalize their system as they likes. It is a fork of Debian so its package manager is *aptitude*, as desktop environment (DE) it comes with XFCE which is lightweight and very customizable. Peppermint doesn't have a lot of beginner-friendly GUIs so users will need to learn the basics using the terminal.

### Debian

The father of a lot of distros, in my opinion one of the best distributions, very stable, community driven, standard of the industry, well documented, etc. The only "hard" thing that Debian has is its installer because for a new user it may be confusing, its installer asks for domain name, root password and other things that a desktop user won't need, the solution to this is to watch a [tutorial](https://www.youtube.com/watch?v=omKFEhWJGYg&pp=ygUNSW5zdGFsIGRlYmlhbg%3D%3D "Tutorial from DistroTube"), follow the steps and you will be ready to go. Debian could be as easy to use as the distros mentioned above by simply installing the default DE tha comes preselected in the installer.

## Bloated

In the Linux environment *bloated* is a subjective term to say that a set of software comes with a lot of useless parts that makes it take more disk space and needs more resources from cpu and ram. A good example is a web browser that comes with a lot of functionalities that may be you already have covered with other software on your PC.

Thats the case for the next 3 distros, they come with a lot of things preinstalled that may be you will never use.

### Elementary OS

It is based on Ubuntu, its DE is Pantheon and is inspired by MacOS while maintaining its unique touch. I don't recommend it.

### Pop_OS!

Developed by System_76, Pop_Os is a distro based in Ubuntu, and it has many features designed to make it easier for new user, in my opinion too many.

### Zorin OS

My problem with Zorin is that it tries to emulate Windows, so far that it could be frustrating for a new user because they are going to try to do everything the same as Windows but a lot of things won't work that way. That may cause someone to stop trying.

### Kali Linux

An other Ubuntu-based; distro this one is focus on security research, it has a lot of related software preinstalled, most of them you will never use, you can just install what you really need.

## Bad

Here are 3 Arch Linux based distributions but can apply to any beginner oriented Arch base distribution.

### Manjaro, Endevour OS, Garuda Linux

Arch is a rolling-realese distribution, means that the updates comes fast to the users it has its benefits, better performance, compatibility with new hardware, get the new features fast, but also its traits as packages comes fast there isn't a lot of time to test them so things will break and patience, experience using terminal and researching will be needed to solve this problems, most of new users lacks on this abilities.

Also some times this distributions comes with an extra package manager, this could cause issues with the dependencies and break your system.

## SUS

The following distros are mostly good, what makes them *sus* is telemetry.

### Ubuntu

Right now telemetry is optional, but there was a time where it wasn't and they didn't say anything until they get caught by the community so I won't trust them a lot.

### Fedora Linux

Since IBM bought Red Hat, they are doing things that actually hurts the FOSS community. The first big one was to stop distributing CentOS as an open source copy of RHEL, and making it a middle step between Fedora and RHEL while also making RHEL closed source, the second one is that there are initiatives to add telemetry to Fedora linux. For me thats enough reasons to do not trust them any more.

### Deepin OS

Is the chinese distribution it is based in Ubuntu, his main characteristic is that has a nice design nothing else.

## Conclusion

In summary, if you want games go with Nobara, if you are a tech savvy person Debian is the best option to learn things, finally for people who don't want to learn about Linux and games aren't a big deal for them Linux Mint is great.

As you learn more about Linux systems you can experiment with different things like building your own DE with server-oriented distros (same distros without any GUI and just the minimal packages) minimal distros like Arch, Gentoo, Void, Artix etc. My recommendation is to do it in a virtual machine (VM) specifically using Qemu with virt-manager, it is faster, lighter in comparison with VirtualBox and more important is open source.
