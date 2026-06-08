# Virtualization

## Overview

EVA uses KVM/QEMU virtualization running directly on Debian Linux.

Rather than using a dedicated virtualization platform, I chose to build directly on Debian to gain a deeper understanding of Linux system administration and the virtualization stack.

Virtual machines are managed through Cockpit with the Machines plugin.

<img width="1903" height="949" alt="image" src="https://github.com/user-attachments/assets/4690a74e-2449-491a-869f-0133f7fcf523" />

<img width="1904" height="356" alt="image" src="https://github.com/user-attachments/assets/133aac43-bfa5-4522-8080-2071146a0ac4" />


## Hypervisor

Host Operating System:

* Debian GNU/Linux

Virtualization Technology:

* KVM
* QEMU
* libvirt

Management Interface:

* Cockpit
* Cockpit Machines

## Virtual Machines

### OPNsense

Purpose:

* Primary router and firewall
* Daily-use gateway for my personal network

Operating System:

* FreeBSD (OPNsense)

Responsibilities:

* Routing
* Firewall management
* Kea DHCP
* Unbound DNS
* Network policy management

This VM is a critical component of the infrastructure and provides connectivity for my personal devices.

### Nextcloud

Purpose:

* Self-hosted cloud platform
* File synchronization and storage

Operating System:

* Ubuntu Server 24.04 LTS

Responsibilities:

* File hosting
* Data synchronization
* Personal cloud services

## Why KVM/QEMU?

I chose KVM/QEMU because it is the native virtualization technology available on Linux.

Using Debian directly allows me to work with:

* libvirt
* Virtual networking
* Linux bridges
* Storage management
* Virtual machine configuration

This approach provides a deeper understanding of how the virtualization stack operates compared to using a dedicated virtualization distribution.

## Networking

Virtual machines are connected through Linux bridges configured on the host.

The OPNsense VM has direct access to both WAN and LAN interfaces, allowing it to function as the primary router for my personal network.

## Future Plans

Potential future additions include:

* Additional service VMs
* Infrastructure monitoring
* Configuration automation
* High-availability experimentation
* Container orchestration

```
```
