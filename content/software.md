+++
title = 'Software'
date = 2024-03-25T15:47:53-05:00
draft = false
type = 'page'
+++

My homelab runs many different things but I do have few constants:

* Operating Systems
  * Ubuntu Server (14-22) LTS
  * Alpine Linux
  * Debian Linux
  * Raspberry Pi OS
  * Windows 10 (so heavy)

Now lets get into the particulars

## Virtualization Stack

### XCP-ng 

Let see, this is easy:
* XCP-ng 8.2.x
* Xen Orchestra (Open Source)

### Proxmox VE

~~I think it was Proxmox VE 7.4-17, but it crashed a while ago.~~

Proxmox v7.4.x & v8.3.x

May 2024: It seems okay now? WTAF! I guess I'll need to upgrade this.


## Virtualized Guests

All these guest are running on the XCP-ng pool.

**Cubes**: This is my testbed for LXC. I also have Docker running inside of an LXC Container and all this is running in a VM on XCP-ng. (Turtles all the way down)
* OS: Ubuntu 22.04 LTS
* LXC/LXD
  * Docker
    * Uptime Kuma
    * Dockge
    * Speedtest Tracker

**LXC001 Host**: This is a VM that is dedicated to running LXC Containers using LXC/LXD. Some of the containers include, Web Servers (Production and Dev), VPN Gateway, haproxy (soonish™). I decided to set this up to see if I need to stay with Proxmox VE just lightweight containers. 
Also, I want to move away from the 'test' environment I created above, that became production.
* OS: Ubuntu 24.04 LTS
* App: LXC/LXD with UI

**GIT**: This is my internal Git Server for local development.
* OS: Ubuntu 22.04 LTS
* App: Gitea

**XOA**: This is my Xen Orchestra VM. It technically not the appliance version of XO but the original test VM was name that so I continued the name..
* OS: Ubuntu 22.04 LTS
* Xen Orchestra from Sources

**Docker001 Host**: VM for hosting docker containers, still working on migrate containers from Cubes (above). \
A joke shouldn't become production (VM>LXC>Docker).
* OS: Ubuntu 2 LTS
* Apps: Docker/Containerd

**Music Server**: Streams audio to Google Home Mini for whole home audio
* OS: Ubuntu: 24.04 LTS (Desktop; xfce)
* Apps: VLC Player

**Collection of mini Alpine VMs**: These are for mini experiments and playing with Ansible

**Other testing**: Windows Boxes, pfSense, haproxy, docker apps, Ubuntu DT - all for testing

## Everything Else

### Information Sphere

***Physical Host Retired. Migrated Services to VM (Unifi) and LXC Containers (Everything Else)***

I'm trying to migrate services into new VM and/or LXC Containers. But for the time being.

* Software
  * OS: Ubuntu 18.04 LTS
  * Apps:
    * NGINX 1.2X Mainline
    * Wireguard
    * UniFi Controller v8
* Web Apps
  * Dokuwiki
  * ~~Nextcloud~~ Discontinue after migrating - not using it.
  * ~~SnipeIT~~ May 2024: Killed it with update, wasn't using it

### Bender

* Software
  * Raspberry Pi OS (Debian Bookworm)
* Services
  * Pi-Hole
    * DHCP
    * DNS

### Marvin

Raspberry Pi; Not yet deployed

* Software
  * Raspberry Pi OS (Debian Bookworm)

### Zapp

Raspberry Pi; Not yet deployed