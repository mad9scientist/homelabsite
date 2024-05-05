+++
title = 'Whole Home Music Streaming - Google Home (DIY)'
date = 2024-05-05T15:11:43-05:00
type = 'post'
+++
**Idea/Project**: Stream audio to multiple Google Home Devices for a whole home audio system. Instead of using a mobile device to stream/control the music, I want to use a container/virtual machine. 

**Background**: I have been streaming background music from a tablet to a single Echo Dot. I have three Google Home devices located around my place, and they can be grouped into a speaker group. Since I don't want to dedicate a tablet solely to play music, especially considering it occasionally stops due to random reboots.

## Experiments

I have experimented with several approaches to achieve this goal. If you have a better idea, please let me know. I will discuss the findings for each of the following attempts.

* Kodi + castnow
* LibreELEC
* VLC Commandline
* mkChromecast + VLC + XFCE4 (Current/Working)

### Kodi + Castnow

I began this project by consulting ChatGPT to gather initial ideas. In short, it suggested some outdated methods which I ultimately abandoned. A more detailed exploration involved using [Kodi](https://kodi.tv) as a media server and integrating it with an NPM module called [castnow](https://github.com/xat/castnow). Initially, I aimed to set this up within an LXC container without a desktop environment, although I later changed this approach.

I opted to move away from this option due to the abandonment of the Castnow module by its author. This led me to explore the next option."

### LibeELEC

I discovered the [LibeELEC](https://libreelec.tv/) project, which offers a version of Kodi designed for embedded devices like Raspberry Pi. They provide a Virtual Machine image in OVA format. This prompted me to learn [how to import an OVA file into Proxmox](/post/import-ova-to-proxmox/). However, after importing the VM disk into Proxmox, the VM wouldn't boot at all.

_So back to the drawing board..._

### VLC CLI

Then I recalled that VLC could stream to Chromecast devices from its UI, at least on Windows. In the current version of VLC, you can even stream to individual devices or Speaker Groups - which is pretty neat.

However, one of the objectives was to accomplish this via CLI on a Ubuntu 22.04 machine. VLC does offer a CLI, prompting me to delve into its documentation. Surprisingly, the [CLI options for VLC](https://wiki.videolan.org/VLC_command-line_help/) are incredibly extensive. I managed to use cvlc to activate one speaker and stream locally stored media, albeit inconsistently. While VLC would activate the speaker with a chime, it was rather random which speaker it would connect to and whether it would play media reliably.

Then, I stumbled upon an interesting discovery: did you know you can stream videos from YouTube in VLC? This seemed promising for the project, as the plan was to stream a live stream to the speakers. However, I found that while you can stream videos from YouTube, you can't stream live streams. Additionally, I encountered another limitation: cvlc requires dbus and other Desktop Environment dependencies to render VLC to Chromecast devices.

After encountering some [problems with Ubuntu 24 (Gnome)](/post/ubuntu-24-04-first-look/) in different project, I opted to experiment with XFCE Desktop ([Xubuntu](https://xubuntu.org/)). Initially, I tried to install XFCE in the LXC container I had been working with, but encountered difficulties. Consequently, I set up a VM with Xubuntu and proceeded to the next attempt."

So to a full desktop install of Ubuntu as a Virtual Machine...

### mkChromecast + XFCE4

This is where I discovered that VLC can stream videos from YouTube with just a URL. While this feature is great, I encountered limitations. Some videos are 'not allowed' to be played back in VLC, and Live Streams won't work as VLC attempts to download the entire video before streaming the audio to the speaker(s).

I found [mkChromecast project](https://mkchromecast.com/) on [GitHub](https://github.com/muammar/mkchromecast).

So mkChromecast is a project that enables casting audio/video to Chromecast devices. I discovered that the system tray does not work consistently, so I opted for the CLI version, which allows streaming any audio to the Chromecast device. The following command works well for my needs.

```bash
mkchromecast -b 192 -c mp3 --sample-rate 44100 -s
# -b Bitrate
# -c encoding
# --sample-rate of 44100Hz
# -s (The most important) Select Speaker(s)
```

Now, I have Firefox playing the live stream while mkChromecast hijacks the dummy audio source and casts the audio to the Google Home Speaker Group.

You can use the Google Home App to control the volume of the audio source, and you can still use the Google Home device for the Google Assistant.

So, I now have my Google Assistant and Whole Home Sound System.

However, I need to find a way to control the audio source without accessing the VM console. Nevertheless, I don't need to change the music that frequently since it's just background music.

If you have any suggestions, please feel free to let me know - via my [contact form](https://mad9scientist.com/contact/) or on [Twitter](https://twitter.com/mad9scientist).

----

If you are interested in what I'm listening to - [Lofi Girl - Synthwave Radio](https://youtu.be/4xDzrJKXOOY)