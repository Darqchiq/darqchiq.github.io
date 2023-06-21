---
title: "How to use SSH"
date: 2023-06-21 22:10:00 +0300
categories: [ssh, linux]
tags: [ssh, linux, tutorial,ubuntu]
image: /assets/img/Posts/ssh.png
---

SSH is a client-server based protocol. This means the protocol allows a device requesting information or services (the client) to connect to another device (the server). When a client connects to a server over SSH, the machine can be controlled like a local computer.
ssh illustration

## Introduction

`SSH` that is also known as Secure Shell or Secure Socket Shell is a protocol or a tool that can be used to connect to a remote computer. SSH enables computers to communicate and share data even in an unsecure network.

SSH works with the client-server model. The computer you are using, to connect with is the “client” and the remote computer you are connecting to, is the `server`. If followed all security precautions, SSH is considered as highly secure.

>In simple words you can use the remote computer using the terminal on your current computer to access and manage resource on the remote computer.

## INSTALLATION & USAGE

Let’s open the command prompt/terminal and type the following command to check if ssh client is installed on your computer or not. This command is used to connect to the remote computer.
The Linux command line is a text interface to your computer. Often referred to as the shell, terminal, console, prompt or various other names, it can give the appearance of being complex and confusing to use.

If you don’t get the the same output, it means that you will need to install it manually. For Windows — you can follow this Microsoft tutorial and for Linux you can follow the below instructions. (I am using Ubuntu for the tutorial).

You will need to enter the following commands to update and install the required packages :
The sudo apt-get update command is used to download package information from all configured sources.

Type `Y` when prompted, it will take some time to install depending on your internet speed.
What are we installing?

`openssh-client` — to connect to remote computers

`openssh-server` — so that your computer can act as a remote computer

Now you can connect to any remote computers. On the remote side the server package should be installed. The SSH service may be disabled by default you will need to start the service manually. You can check the status of the service using the following command :
We use systemctl status command under systemd to view the status of the given service on Linux operating systems.

As you can see above the status is inactive(dead). Now, hit the following commands to start the service and enable it so that you don’t have to start it again and again after boot :
SSH or Secure Shell is a network communication protocol that enables two computers to communicate (c.f http or hypertext transfer protocol, which is the protocol used to transfer hypertext such as web pages) and share data.

So you have successfully configured your remote system but if you have UFW (Uncomplicated Firewall) installed on your distro you will need to hit the following command in order to allow `ssh` to work perfectly :
Uncomplicated Firewall is a program for managing a netfilter firewall designed to be easy to use. It uses a command-line interface consisting of a small number of simple commands, and uses iptables for configuration.

Woooo!! If you followed the tutorial right everything is done on both client and server side. Now to it’s time to get your hands dirty and connect to a remote computer.

I will connect to my raspberry pi 4 and use it headless (without any display or keyboard/mouse) which is connected through a ethernet. You can use any computer to connect to. NOTE : The example below will follow for in a devices in a same network. To connect to a device outside a network we need to forward the port 22, I think that’s a tutorial for another day.

I switched ON my pi and now lets connect it with my current computer that is ubuntu. Below is the syntax to follow to connect to a system, where username is the username that you wish to connect to which is present on the remote system. And ip-address is the local ip (in our case) that is assigned to that device by the wifi router. To find the ip address of the remote system you can visit the default gateway of your router. Mine is 192.168.0.1

```bash
ssh username@ip-address
```

In my case it will be :

```bash
ssh pi@192.168.0.103
```

where `pi` is the username and `192.168.0.103` is the ip of the raspberry pi(the remote computer)

>NOTE : The above command remains the same for windows and linux

Following is a short gif that illustrates on how I connected to my Pi.
Ubuntu is a Linux distribution based on Debian and composed mostly of free and open-source software. Raspberry Pi is a series of small single-board computers (SBCs) developed in the United Kingdom by the Raspberry Pi Foundation in association with Broadcom.

So, in these way we can use ssh to connect to different computers. If you are using AWS you should start using ssh to connect to your AWS instance. SSH has many more advantages like avoid attacks such as packet sniffing.

If you are not so familiar on using the terminal you can use application like PUTTY which is available for both Windows and Linux.

## CONCLUSION

>So in these blog we learned about ssh and how to install it on a Ubuntu system. How to connect to various remote computers in same network. This was just a basic tutorial, we will learn more about ssh commands and functions in the next tutorial.