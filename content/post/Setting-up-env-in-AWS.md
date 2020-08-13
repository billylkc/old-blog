---
title: "Setting up working environment on AWS"
date: 2020-08-10T06:10:10+08:00
thumbnailImage: /images/getting-started.jpg
draft: false
categories:
- setup
- linux
tags:
- getting started
- cloud
- linux
---

> As cornerstones of scientific processes, reproducibility and replicability ensure results can be verified and trusted.

## Summary
* [Introduction](#introduction)
* [Create virtual machine on AWS](#create-a-virtual-machine-on-aws)
* [Set up SSH keys](#set-up-ssh-keys)
* [Connect with Putty](#connect-with-putty)

## Introduction

When you are working in a team, you may want to have a stable environment, so everyone can easily access your analysis findings, and reproduce the result.
Windows may be good for our day to day work, but when it comes to stability and reproducibility, it may not be working as well as their Linux counterparts.

If you are having troubles in setting up a Data Science working environment or installing packages/dependencies, or maintaining your analysis project, read on. Give yourself a try with a Linux server, and set it up for free (For a year, at least ㋡) on AWS.


## Create a virtual machine on AWS

Setting up a virtual machine on Cloud environment is easier than ever. Most cloud providers (AWS, GCP, Azure) are providing free credits for new users. Today we are going to setup an Amazone **EC2 Ubuntu machine** on AWS using a free-tier account.

![Setting up on AWS](/images/gif/aws-setup.gif)


_Key steps_
* Go to Amazon Web Service - [here](https://aws.amazon.com/free)
* Assume you have already signed up for an AWS account
* Login to your account by clicking _Sign in to the Console_ at the top right corner
* Go to All services > Compute > E2
* Launch an _Ubuntu (x86) Instance_
* Choose the _t2 micro instance_ (1 vCPU, 1 GB Ram, 8Gb Storage)
* Launch Instance with default settings
* Create a new key pairs (**Important!** -  _Download Key Pairs_ for later use)
* Wait the Instance to be Initiated (Can take a few minutes)
* TA-TA

## Set up SSH keys

Some description about ssh key

![Setting up on SSH](/images/gif/set-up-ssh.gif)

_Key steps_
* Download and install Putty (putty-64bit-0.74-installer.msi) - [here](https://www.putty.org/)
* Download PuttyGen - [here](https://www.puttygen.com/download.php?val=49)
* Run PuttyGen
* Convert the previously generated key pairs to a private key
  * _Load_ your _pem file_ (e.g. _billy-vm.pem_). Make sure the file type is set to _All Files(\*.\*)_, so you can see the file.
  * Click _Save private key_. And save to a secure location. (Can also save to <home_dir>/.ssh, `e.g. C:/Users/Billy/.ssh/billy-vm.ppk`)

## Connect with Putty

Finally, we get to the part to actually connect to our virtual machine.

![Connect to VM](/images/gif/ssh-to-vm.gif)

_Key steps_
* Copy the _Public DNS_ of your instance
* Open _Putty_
* Go to _Connection > Expand SSH > Auth_
* Browse the _Private key_ (e.g. ~/.ssh/billy-vm.pkk)
* Go back to Session setting
* Set Hostname to _ubuntu@\<your public domain\>_ (Remember to add ubuntu@)
* Set Saved Session to some name (e.g. billy-vm)
* _Save and Connect_ to the VM
* Should be able to see Welcome to _Ubuntu 18.04.5 LTS in your Putty session_

&nbsp;

Photo by [Lindsay Henwood](https://unsplash.com/@lindsayhenwood) on Unsplash
