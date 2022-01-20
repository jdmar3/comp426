---
title: "Software setup for Windows"
description: "Instructions for installing required software on Windows"
---

To be a successful web developer in COMP 426, you'll need to install some software on your computer.
Follow the guide on this page if you have a Windows computer.

## Chrome Web Browser
Your projects in this course will run in a web browser.
While most web browsers should work, we only support and test in the Google Chrome web browser.
Install it by following the instructions below.
We suggest making it your computer's default web browser.

1. Follow this link: [https://www.google.com/chrome/](https://www.google.com/chrome/)
2. Select "Download Chrome"
3. Accept the Agreement
4. Open the ChromeSetup.exe installer and press "Yes" if prompted for permission to install

## Text editor

This semester, we will write all assignment code using either VSCode or VIM or both!

### Visual Studio Code (VSCode)

1. Follow this link: [https://code.visualstudio.com/#alt-downloads](https://code.visualstudio.com/#alt-downloads)
2. Download the Windows installer
![screenshot of vsc download page](http://s3.amazonaws.com/110-2015-fall/4.png)
3. Open the downloaded installer

### VIM

Follow the instructions in this tutorial for installing VIM on Windows:

https://linuxhint.com/install-vim-editor-on-windows/

## Windows Subsystem for Linux

[Windows Subsystem for Linux (WSL)](https://docs.microsoft.com/en-us/windows/wsl/) lets you run a Linux development environment on Windows and access it from VSCode. 

My recommendation is that you use Debian 11 as your chosen distro. 

Follow the instructions here to install it:

https://docs.microsoft.com/en-us/windows/wsl/install

See this link for an overview of getting started with using WSL in VSCode:

https://code.visualstudio.com/docs/remote/wsl#_getting-started

### Install required software in WSL

#### Node.js

Follow the instructions in this tutorial for installing Node and related packages in WSL:

https://docs.microsoft.com/en-us/windows/dev-environment/javascript/nodejs-on-wsl

#### git

If you are using Debian or a Debian-based distro like Ubuntu in your WSL, you can use `apt` to install software, like git.

Follow the instructions in this tutorial for installing Git in WSL:

https://docs.microsoft.com/en-us/windows/wsl/tutorials/wsl-git

## Direct install in Windows

If you wish to also install Node and git in Windows natively (not a bad idea to have them available), you can see how to do that below.

### node.js - JavaScript Runtime
1. Follow this link: [https://nodejs.org/en/download](https://nodejs.org/en/download)
2. Select the "Windows Installer" under the LTS tab.
If given the option, select the 64-bit option.
![screenshot of node.js download page](http://s3.amazonaws.com/110-2015-fall/1.png)
3. After the download completes, open the installer.
4. Continue through the installation screens using the default settings until the install is complete.

### git and bash - Developer Tools
1. Follow this link: [https://git-scm.com/downloads](https://git-scm.com/downloads)
2. Select "Windows"
![screenshot of git download page](http://s3.amazonaws.com/110-2015-fall/2.png)
3. After the download completes, open it.
4. Continue through the installation screens using the default settings until the install is complete.

[Return to a00 main page](a/00)
