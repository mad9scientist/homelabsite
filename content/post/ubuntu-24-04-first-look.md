+++
title = 'Ubuntu 24.04 LTS - First Quick Look'
date = 2024-05-05T13:29:00-05:00
type = 'post'
+++
Ubuntu 24.04 LTS (Ubuntu 24) was released at the end of April. I have some thoughts about this release. The main reason I'm 'reviewing' this release is because I'm going to be using this particular version for the basis of my production servers. I want to gain some hands-on experience before deploying it to production.

I decided to test the desktop versions (Gnome & XFCE) of Ubuntu 24 in Proxmox 7.4 (I know it is out of date), which may be related to some _issues_, detailed below.

First of all, the new installer is neat but doesn't matter to me because I tend to clone a template or use LXC containers for most of my projects. So I don't see the installer that much. Since administer headless server, I spend most of my time on Ubuntu in the CLI, so there's that.

So right off the bat, I ran into a problem after the first reboot. I reached the login screen, logged in, but then the screen would go black and return to the login screen, flashing back and forth between the two. I encountered this behavior on both Gnome and XFCE. However, to access the Gnome install, I had to force a reset multiple times to trigger a crash detection and receive a report prompt. 

On XFCE (Xubuntu), I have a similar issue, but I don't have to crash the machine. The issue I'm experiencing is that I boot up to the login screen, enter my login details, 'click' login, the screen goes black, and after a few seconds returns to the login screen. I log in again - it does the same black screen back to the login screen - it repeats this two or four times before getting to the desktop. I was testing the XFCE variation for [another project](/post/music-streaming-server/). It's an annoyance, but I can live with it, as of the date of this article I'm still using that VM.

I will admit that using Proxmox VE 7.4 may be related to this problem. But I have not yet tested it in the XCP-ng cluster - _yet_. I will post an update when I get around to that.

I have not yet tested the Server Release, but I will soon™.