---
title: "mod2 Javascript + NPM"
description: ""
draft: true
weight: 20
enableToc: true
tocLevels: ["h2", "h3", "h4"]
---

### Download Dependencies

The COMP 426 code that you downloaded uses a few "dependencies." Dependencies are another word for additional libraries and packages written by third-party developers that are required and used internally by the COMP 426 code.
In the early days of programming, managing dependencies was time consuming and difficult.
Luckily, nowadays Node.js comes with a fantastic built-in tool, called Node Package Manager (npm), which is designed to automatically manage JavaScript dependencies for you.

Npm is a command line tool, which means it only works through the terminal (aka command line).
We'll learn a lot more about how to use npm later in the semester, but for now we'll use its most basic fundamental feature: automatically selecting and downloading all relevant libraries to your computer.

> This course requires basic familiarity with the terminal, especially for using tools like npm.
> Don't worry if you don't feel comfortable with the terminal just yet---the assignment guides will walk you through the most important commands.
> In the long run, however, having a working knowledge of the command line is a very valuable skill, especially for aspiring software engineers.
> With this in mind, it may benefit you to make sure you fully understand every command we use.
> If you're looking to learn more about using the terminal, the [linux commands cheat sheet](https://www.linuxtrainingacademy.com/linux-commands-cheat-sheet/) is a great resource.

The following steps guide you through opening a terminal window from Visual Studio Code and using npm to automatically install dependencies.

1. To open a terminal from Visual Studio Code, open the "View" menu and select "Integrated Terminal" (or just "Terminal" on Mac).
2. A new terminal window should have opened in the bottom panel of Visual Studio Code.
Type the following command into the terminal and then press enter:
```bash  
$ npm install
```
3. Wait for this process to complete.
If warnings appear in the terminal, it's safe to ignore them.

> The command `npm install` tells npm to look in the file named `package.json`, which should contain a list of dependencies to install, and install these dependencies.
By default, the downloaded dependencies are placed into a special directory named `node_modules`.
After the command completes, you should be able to find both `package.json` and `node_modules` in the left side panel of Visual Studio Code.
Try clicking on them to see what's inside.

Again, we'll learn a lot more about how to use npm in a later assignment ([a02](assignment/a02), to be exact).

## More about npm *(Optional)*

This section introduces you to a few new npm commands. While this material isn't required for the assignment, it may come in handy in the future!


### Updating dependencies

The dependencies that you add to your application may change over time. Each dependent package is owned and maintained by a different developer or team of developers, and many of these packages are actively being improved. This means that occasionally the maintainer of a package may release a new version of the code with bug fixes, new features, or code improvements. Every once and a while, you may want to make sure that your app is using the newest version of the dependencies. Luckily, npm makes this easy. Simply run the following command from a terminal pointed at your app's root folder.

```bash
$ npm update
```

The process may take a few seconds or minutes to complete, but when its done all of your dependencies will be up to date!


### Removing a dependency

If you ever encounter a situation where you have installed a dependency that you later realize you do not need, you can use the `npm uninstall` command to remove the package both from the `node_modules` folder and from the `package.json` file.

```bash
$ npm uninstall package-name-here
```


### About `package.json` and `package-lock.json`

We talked a little about `package.json` back in a00. It's a special configuration file created when you run `npm init`, and it contains various information about your project. Inside `package.json` is a list of all the packages that your app depends on. This list is managed by npm, and it gets updated whenever you run `npm install` or `npm uninstall`. You can open `package.json` and view the current dependency list at any time. In a02's `package.json`, you should see `bulma` and `browser-sync` listed as dependencies.

You may have noticed another file also appear in your project directory: `package-lock.json`. This is  another special configuration file created by npm and used to manage your app's active dependencies. In particular, `package-lock.json` exhaustively lists the *version* of every package used by your app. This file comes in handy when you develop on multiple different computers, because it ensures that every system shares the exact same version of the exact same dependencies. Without `package-lock.json`, it would be possible for different machines to run different versions of the same dependencies, potentially causing inconsistencies at runtime.

> `package-lock.json` is updated when you run `npm update` to reflect the new versions of updated dependencies.


### Local vs global npm packages

So far, we have used the `npm install package-name-here` to install new packages to our `package.json` file. *Packages installed in this way are installed locally to the app in the current directory.* This means that **the folder at which your terminal points matters a lot**, because it determines (1) where the dependency will be installed and (2) which `package.json` it will be attached to.

There is also a way to *globally* install a package:
```bash
$ npm install -g browser-sync
```
The `-g` in this command tells npm to install the `browser-sync` package to a special, hidden, system-wide `package.json`. Running the command like this will **not** install the package to the local `node_module`, or update the local `package.json`. The benefit of this approach for packages like Browsersync is that you can install them one time globally and then access them from anywhere.
