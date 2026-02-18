+++
title = 'Services'
date = 2024-03-25T18:02:54-05:00
draft = false
type = 'page'
+++

Here's a list of services I run in my homelab in 'production'

* Web Services (NGINX+PHP+MariaDB)
  * [FreshRSS](https://freshrss.org/) - RSS Reader
  * [Dokuwiki](https://www.dokuwiki.org/) - Internal Information Management/KB
  * ~~[Nextcloud](https://nextcloud.com/)~~ Discontinued
* Network Services
  * Ubiquiti - UniFi Controller
  * Ubiquiti - UISP Network Management System
  * [Pi-Hole](https://pi-hole.net) (DNSBL + DHCP)
  * [WireGuard](https://wireguard.com) VPN (Not Tailscale)
  * PXE Boot - via [Netboot.xyz](https://netboot.xyz) - Testing/Discontinuing?
* [Gitea](https://about.gitea.com/) - Local Code Repo
  * Gitea Runner/Actions
* [OctoPrint](https://octoprint.org/) 3D Printer Web Interface (Ender 3 Pro)
* [Music Streaming](/post/music-streaming-server/) (Not a Media Server)
* Docker Hosts
  * ~~Portainer~~ [Dockge](https://dockge.kuma.pet/)
  * [Uptime Kuma](https://uptime.kuma.pet/)
  * [Speedtest Tracker](https://docs.speedtest-tracker.dev/)
  * [OpenSpeedTest](https://openspeedtest.com/)
  * [Enclosed](https://enclosed.cc/)
  * Calibre-Web - Testing
* LXC/LXD Hosts (CTs)
  * Ansible Control Host
  * Cloudflare Tunnel Host
  * Docker Host (This is stupid, don't do it)
  * Email Backup Container (imap-backup)
  * HA Proxy (Reverse Proxy)
* Testing/Toys
  * VoIP PBX (Evaluating)
    * [FusionPBX](https://www.fusionpbx.com/)
    * [FreePBX](https://www.freepbx.org/)
  * DNS (Internal Use/Test)
    * [BIND9](https://www.isc.org/bind)
    * PowerDNS
  * [Home Assistant](https://www.home-assistant.io) - Smart Home Controls
