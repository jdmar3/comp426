---
title: "git"
description: "Save your your whole workflow (and your sanity) with git. Never lose edits again."
draft: false
weight: 0
enableToc: true
tocLevels: ["h2", "h3", "h4"]
---

**git** is a distributed version control system that keeps track of the changes between plaintext source files. It can be used for collaboration or for managing and keeping track of workflows for individuals. While primarily intended for software source code, git works with any plaintext files, and so can also be used for authoring of other kinds.

## git basics

[git official documentation](https://git-scm.com/docs/)

You should become conversant with the official documentation for git.
It has everything you need to know, all in one place.

[git - The Simple Guide](https://rogerdudler.github.io/git-guide/) [(Download PDF)](http://rogerdudler.github.io/git-guide/files/git_cheat_sheet.pdf)

The guide above is, hands down, the best, most straightfoward guide to get you going or refresh your memory for git commands. 

[An Ultimate Guide to git and GitHub - Suhail Kakar](https://dev.to/suhailkakar/an-ultimate-guide-to-    git-and-github-20j)

<a href="https://education.github.com/git-cheat-sheet-education.pdf" target="_blank">Git Cheat Sheet - GitHub</a>

<a href="https://www.atlassian.com/git/tutorials/" target="_blank">Git Tutorials and Training - Atlassian</a>

## Using gitignore

You can place a file in the root of your repository directory named `.gitignore` and add paths which will be specifically excluded by git when you add files and commit changes. This is a good idea to do with Node.js packages in particular, since otherwise you are just moving around a bunch of dependencices that can be automatically downloaded by npm instead.

[How to add folder to gitignore - Edpresso Team](https://www.educative.io/edpresso/how-to-add-folder-to-gitignore)

[A collection of `.gitignore` templates](https://github.com/github/gitignore)

This is a good resource.
You will likely want to add the text from [Node.gitignore](https://github.com/github/gitignore/blob/master/Node.gitignore) to your `.gitignore` file for most assignments.
