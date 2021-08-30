---
title: "Software setup for Linux"
description: "Instructions for installing required software on Linux"
draft: true
---

To be a successful web developer in COMP 426, you'll need to install some software on your computer.
Follow the guide on this page if you run Linux.

Before you start: make sure that your repositories are up to date and your system is upgraded.

On Debian/Ubuntu:

```{bash}
sudo apt update
sudo apt upgrade
```

On Fedora/openSUSE:

```{bash}

```

## Chrome Web Browser
Your projects in this course will run in a web browser.
While most web browsers should work, we only support and test in the Google Chrome web browser.
Install it by following the instructions below.
We suggest making it your computer's default web browser.

1. Follow this link: [https://www.google.com/chrome/](https://www.google.com/chrome/)
2. Select "Download Chrome."
3. Select the correct download package for your system.
4. Accept the Agreement.
5. Save the download package. 
6. Open a terminal and `cd` to the location of the saved download package.
	1. If you are running Debian/Ubuntu, run `sudo dpkg -i google-chrome-stable*.deb`
	2. If you are running Fedora/openSUSE, become root using `su` and then run `rpm -i google-chrome-stable*.deb`
7. 

## node.js - JavaScript Runtime
1. Follow this link: [https://nodejs.org/en/download/](https://nodejs.org/en/download/)
2. Select the "Macintosh Installer" under the LTS tab.
3. After the download completes, open the installer.
4. Follow the installation instructions using the default settings to completion.


## git - Developer Tools
1. Click on the Spotlight icon, the magnifying glass in the top right corner of your screen (or press Command+Space)
2. Type in the word "Terminal" and press Enter
3. In the window that pops up, type in the word "git" and press enter.
You will be prompted to install Command Line Developer Tools.
Agree to this, even if you are on battery power.
Let the installation complete.


## Visual Studio Code - Programming Text Editor
This semester, we will write all assignment code using the Visual Studio Code editor.

1. Follow this link: [https://code.visualstudio.com/#alt-downloads](https://code.visualstudio.com/#alt-downloads)
2. Download the Mac zip file
![screenshot of vsc download page](http://s3.amazonaws.com/110-2015-fall/5.png)
3. Double click the downloaded "VSCode-darwin-stable.zip" file.
This extracts and creates an application named "Visual Studio Code" in your downloads folder.
4. Drag the "Visual Studio Code" file from your Downloads folder to your Applications folder.
You should see the Applications folder in the left-hand sidebar of your Finder window.

[Return to a00 main page](assignment/a00)
