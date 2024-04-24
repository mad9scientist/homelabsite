+++
title = 'Docker in LXC in a VM on Actual Hardware - WTF'
date = 2024-04-01T00:24:09-05:00
draft = true
type = 'post'
+++

Have you ever do something, just to see if it was possible?

Well, that is how I ended up with this,

> Could you run docker containers inside of an LXC container, thats an Virtual Machine??

Well the short answer is; yes, yes you can. How to get there is a bit of a chore, but it is definetly doable. 

> Disclaimer: DO NOT, I repeat, DO NOT DO THIS IN PRODUCTION!

So I'm going to glaze over the following steps, and focus only one getting to Docker to work in LXC (jump to section)

## Prereqs

So when through the steps to setup an Ubuntu 22.04 Virtual Machine (VM) in XCP-ng and had a setup Ubuntu Server. Then I installed LXC and LXD snaps (see LXC/LXD Docs). 

Then I created an Ubuntu LXC Container.

Now on to Docker...

## Setting up Docker inside of LXC

Now we are going to shell into our fresh <s>victim</s> LXC Container. 


> Warning: If you do this, please make sure your VM and LXC Storage Drive have a lot more storage than you think it should. I have been biten multiple times while playing with Docker of running out of space.
The number of times I have gone to pull down a new Docker App to play with and next thing I know my LXC Host crashes because the contains have fill the drive. *screams*



> Steps to configure the LXC container as Privileged
``` bash
lxc config set container-name security.privileged true
```
Note: Please note that by giving a LXC container this privilege, you have just increase your secruity risk. Now it something compromises the Container (in this case via Docker). The Host (LXC Machine) is directly vulnable. So as I said earlier - DO NOT, REPEAT, DO NOT DO THIS IN PRODUCTION. Lab environment, fine, whatever. Publicly Exposed Environment - HELL NO.
To quote the LXD Docs directly
> Note however that in this case the root user in the container is the root user on the host.

> Install Docker via Docker Docs
> Test using Hello World and Portainer 

## Resources

  * Ubuntu LXC/LXD Documentation
    * [Ubuntu Server Docs: Container - LXC](https://ubuntu.com/server/docs/lxc)
    * [Ubuntu Server Docs: Container - LXD](https://ubuntu.com/server/docs/lxd)
  * LXD Docs
  * Docker Install Docs

