---
author: "Mario Chavez"
title: "Setup WSL for development"
description: "I made a guide to install and setup WSL because I always have problems"
date: 2022-11-13
image: /images/blogs/wsl-setup/wsl-screenshot.jpg
draft: false
tags:
    - wsl
    - windows
    - ubuntu
    - development
toc:
---

So you want to develop with Linux but also use some Windows exclusive software (games)? That was my case so I tried some of the alternatives dual-booting, game on Linux, use PowerShell, virtual machines (I didn't try PCI passthrough with a Windows vm because it need 2 gpus).

The sustainable solution I've found is to use Windows as my man OS and put al my programming stuff in WSL, but it has a little inconveniences.

I'll explain the process to install WSL to development and how to get rid of that inconveniences.

<!-- **Why should you use WSL?**

- It's a friendly introduction to Linux.
- Learning a new operative system will improve your understanding of how computers really works.
- It can improve your workflow.
- Most of the computers in the world are running Linux.
- To look cool on the internet. -->

## Setting up Windows

First we need to change some settings in Window. Now we go to `Settings > Update & Security > For developers` and activate `Developer Mode`.

Then we go to `Control Panel > Programs > Turn Windows features on and off` here we check the box of **Hyper-V** (I activate **Hyper-V** because some times I have problems if is not enabled) and **Window Subsystem for Linux**. *Btw here you can uncheck Internet Explorer 11 if you want.*

## Download WSL

### The easy way

In PowerShell type

``` Powershell
wsl --install
```

it will download the default distro that is Ubuntu.

### If it did not work

It happens to me that WSL2 have not been downloaded just by checking the option, thats why I use an [installer](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi) from Microsoft that I found in a [guide to in install WSL](https://learn.microsoft.com/en-us/windows/wsl/install-manual#step-4---download-the-linux-kernel-update-package) in older versions.

Then when the installer ends we have to set more configurations, so open **PowerShell** or **CMD** and type:

``` powershell
wsl --set-default-version 2
```

This will set WSL2 as default so we don't run WSL1 that is slower and has less compatibility. Now we have to update our kernel with the next command:

``` powershell
wsl --update
```

Finally we check the status with:

``` powershell
wsl --status
```

## Download Linux distribution

There are some different ways to install various Linux Distributions, but I just cover the **Microsoft Store** way, so just search for the word *"wsl"* and you will get some results:

- **Ubuntu:** I use this because it downloads a relative recent version of Ubuntu.
  - **Ubuntu (Preview):** It's a newer version of Ubuntu but it can be unstable.
  - **Ubuntu XX.XX.X LTS:** This are older versions that can be less compatible.
- **Debian:** I prefer this but the version in the store is too old and I had a lot of compatibility problems.
- **Kali Linux:** A distribution base in Debian and it comes with a lot of security oriented software already installed.
- **openSUSE:** I haven't use this distribution.

Now choose your preferred one and click `Get`, wait till is downloaded and click in `Open` and a terminal will aper with this message `Installing, this may take a few minutes...` just wait till is installed then the terminal will ask you for `Enter new UNIX username:` then `New password:` and a confirmation.

Congratulation you have successfully installed WSL.

## The "inconveniences"

First one and the biggest, a lot of times if you leave turn on WSL for a long time a process named **Vmmem** will take the 100% of ram and/or 100% of cpu usage, some times you can still use your pc but others the PC gets unusable, the quick fix is to just run the command `wsl --shutdown` in PowerShell the permanent one has some step but is as easy.

- First to *C:\Users\{YOUR_USER}*
- Then create a file named ".wslconfig"
- Inside the file write the next lines

```config
[wsl2]
# Max memory usage by WSL
memory=3GB
# Max cores will be used by WSL
processors=4
```

Thats all after a restart the changes will be applied.

The next are some minor problems relate to the nature of virtual machines. The one I found is that if you try to use a drive with **exFAT** file system to work and run some executables you will have a hard time because the WSL/Linux permission system only works over **NFTS** so take care of that and format your drives as you want.

## Setting up your distribution

Now that you have open your Linux environment I'll give you some useful tips to your first steps. Most of the distros in the store are debian based so I'll give the command to Debian base systems.

First update our system. This will update the database of our system and upgrade the upgradable packages.

``` bash
sudo apt update && sudo apt upgrade
```

Then install some useful packages, **nala** is a frontend for aptitude(the package manager of Debian based systems) that is more readable and has faster download, just use `nala` instead of `apt`, **vim** is a keyboard oriented text editor but it can be a bit hard at first, **nano** other text editor but is more "friendly" and **neofetch** it displays system information.

``` bash
sudo apt install nala vim nano git neofetch
```

Also to save some time ad this to your **.gitconfig** file (if doesn't exist create it with `touche .gitconfig`) if you are going to work with git, just replace the fields with your own information.

``` git
[user]
        email = mailexample@mail.com
        name = Name Example
[core]
        editor = aTextEditor
```

So now run `neofetch` to look cool on the internet. You can use Windows Terminal with WSL, also you can run WSL in Visual Studio code and add the WSL extension to improve your work flow. I would recommend you to research about symbolic links should be useful to improve your workflow, also about package managers, aliases, commands in bash. Using and understanding Linux operative systems is really fun and interesting hope you also get more interested in this topic just by using WSL.

Thanks for reading hope it's useful for you.
