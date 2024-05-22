+++
title = 'Hardware'
date = 2024-03-25T15:47:43-05:00
draft = false
type = 'page'
+++

Here is a quick summary of the hardware that makes up my HomeLab. It's not much, but it's my...

## Virtualized Machines

### XCP-ng

This is my XCP-ng testing pool that is running <s>most</s> all of my virtualization services. I use Xen Orchestra, self complied version, to manage the pool and VMs. 

Pool Version: XCP-ng v8.2.1

#### XCP1

Specs
* Dell OptiPlex 3010
  * Intel Core i5 3450 @ 3.10 (4 Cores/4 Threads)
  * 8GB DDR3?
  * 400GB Spinning Rust

#### XCP2

Specs
* Lenovo 10TX008XUS
  * Intel Core i5-8500 @ 3.0GHz (6 Cores/6 Threads)
  * 16GB DDR4
  * 80GB Spinning Rust

### Proxmox VE

This was the first Level0(??) Hypervisor I started with, but some how set it up with an all SSD storage configuration. ~~However, in early 2024 I stopped using it because the main drive started throwing errors after few days of uptime.~~ Well, it started working again without problems now - I'm currently using it for ansible testing.

#### PVE

Specs
* Lenovo H530 Desktop
  * AMD A10-6700 @ 3.7-4.3GHz @ 3.7-4.3GHz (4 Cores/4 Threads)
  * 8GB DDR (6.9GB Available)
  * Storage
    * 128GB PNY SSD (boot)
    * 512GB Inland SSD (Extra)
* Proxmox VE 7.4-18

#### vhost002-pve

In May 2024 I added another Proxmox host to make a two member cluster (I know it's not really a cluster - blah blah).

Specs
* HP Pavilion SFF 400-224
  * AMD A4-5000 @ 3.7-4.3GHz (4 Cores/4 Threads) BGA
  * 8GB DDR3-1600U
  * 1TB Spinning Rust
* Proxmox 8.2.2

## App Server

General App Server and first machine to be implemented as homelab.

### Information Sphere

This is a Hosted UniFi Controller, WireGuard VPN Server, NGINX Web Server and ZeroTier Router.

Specs
* Dell Dimension
* Pentium 4 @ 2.8GHz HT
* 2GB DDR
* 128GB PNY SSD
* FE Ethernet

Future Project: Migrate to Containers and VM


## Raspberry Pi (RPi)

Do you even have a homelab if you don't have any Raspberry Pis?

### Bender

This is my Pi-Hole (DNS) and DHCP Server. This is the second revision of this machine, it was called Fry but it needed an OS Update, hence Bender. Soon™ Zapp and Kif will join Bender as redundant/backup DNS servers running BIND9.

Specs
* Raspberry Pi 3 Model B Rev 1.2
* 32GB SD Card

### Zapp

Upcoming multiple level project. Offline while working on Ansible Playbook.

Involved Projects: 
* IP Scheme Change
* DHCP
* BIND9 DNS
* NTP
* Highly Available/Redundancy

Spec
* Raspberry Pi Zero 2 W
* 32GB SD Card
* Wireless

### Marvin

Currently offline, but planned to run some services in LXC containers.

Spec
* Raspberry Pi 4 (8GB)
* ~64GB SD Card

## NAS

* WD MyCloud Mirror 3TB

Uses as shared storage for the XCP-ng Pool and some network storage.