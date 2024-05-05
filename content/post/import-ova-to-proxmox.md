+++
title = 'Import OVA/OVF into Proxmox VE'
date = 2024-05-04T15:09:24-05:00
type = 'post'
+++
1. Download the OVA/OVF to the proxmox host
2. Unzip/Extract OVA to expose vmdk and OVF
    * You many need to ``apt install unzip``
3. Shell to the Proxmox Host to the directory of the OVF/VMDK
4. Use the following command
```bash
qm importovf {vmid} {OVA/OVF Filename}.ovf {target storage}
```
To import to VM 101 with the ovf named web101.ovf to the vmdata storage location
```bash
qm importovf 101 web101.ovf vmdata
```
``!! Note: VM should not already exist !!``

5. Switch back to PVE Web Interface and add networking and any other VM changes
6. Done - Start VM and enjoy

## Source
* https://pve.proxmox.com/wiki/Migrate_to_Proxmox_VE#Migration (Import OVF)

Tested on: PVE 7.4-17