---
title: "Why Git? Learn how to setup in 10 minutes"
date: 2020-08-16T18:45:20+08:00
thumbnailImage: /images/git-intro.jpg
draft: false
categories:
- git
tags:
- getting-started
- git
- devops
keywords:
- ds
- devops
---
> Version control enables developers to move faster and it allows software teams to preserve efficiency and agility as the team scales.
<!--more-->

## Summary
* [Introduction](#introduction)
* [Install Git client](#install-git-client)
* [Set up account](#set-up-account)
* [Set up SSH key](#set-up-ssh-keys)
* [Initiate a repository](intitate-a-repository)
* [First commit](#first-commit)
* [Other useful Git commands](#other-useful-git-commands)
* [Final words](#final-words)

## Introduction

Keeping track of changes of your project is crucial, especially when you are collaborating with others. Having a way to know what changed in a file when and by whom, will help you adapt and be as lean as possible in the current fast-moving business evnvironment.

While these version control tools make tracking changes easy, learning them can be hard. Let's clear up what Git can bring us, and learn it in a quick and painless way.

## Install Git client
_Windows_

* Download Git - [Here](https://git-scm.com/download/win)
* Run the installer, leave all settings as default
* Run Git Bash
* Type in the command
  ```
  git version
  ```
* Should be able to see the following message
  ```
  git version 2.28.0.windows.1
  ```


![Install git client](/images/gif/set-up-git.gif)


_Linux (Ubuntu)_

To be added

## Set up account

* Go to github.com - [Here](https://github.com/)
* Register your account

![Register git](/images/gif/register-git.gif)

## Set up SSH key

* Sign in to your github account
* Go to top right corner > Settings > SSH and GPG keys
* Follow the __generating SSH keys__ guide - [Here](https://docs.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
* Open Git Bash, and enter this command
  ```
  ssh-keygen -t rsa -b 4096 -C "<Your email>"
  ```
* Save the key under your ~/.ssh directory, e.g.
  ```
  /c/Users/Maximus/.ssh/id_rsa_demo
  ```
* Use empty passphase for now
* Find your key in the ~/.ssh folder, there would be two files generated
  * __id_rsa_demo__ (private key, keep it safe)
  * __id_rsa_demo.pub__ (public key)
* Go back to the previous page > __New SSH key__
* Add new key with the following settings
  * Title: my-demo-ssh (Or any names)
  * Key: __\<Paste the content inside the id_rsa_demo.pub file\>__
* Final step, create a __config__ file under __~/.ssh__ folder
* Save the content of the file according to the following (Change accordingly)
  ```
  Host <profile name>
        HostName github.com
        User <Username>
        IdentityFile <Path of your ssh file>
  ```

  _Example_
  ```
  Host github.com-billylkc-demo
        HostName github.com
        User billylkc-demo
        IdentityFile ~/.ssh/id_rsa_demo
  ```

&nbsp;
![Set up SSH key](/images/gif/git-ssh.gif)


## Initiate a repository

## First commit

## Other useful Git commands

## Final words

Write sth

&nbsp;

Photo by [Yancy Min](https://unsplash.com/@yancymin) on Unsplash
