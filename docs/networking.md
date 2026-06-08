# Networking

## Overview

EVA hosts an OPNsense virtual machine that serves as my primary router and firewall.

Although the ISP router remains connected to the internet connection, all of my personal devices are connected through OPNsense. The ISP router is only used to provide upstream internet access to EVA.

OPNsense is used daily and is responsible for routing, firewall management, and DHCP services for my personal network.

<img width="1903" height="949" alt="image" src="https://github.com/user-attachments/assets/ff6b56ab-34b1-4db5-9469-925bb4097dc7" />

<img width="1904" height="356" alt="image" src="https://github.com/user-attachments/assets/aa32204a-0409-4885-b496-78fdca5fa641" />


## Network Topology

```text
Internet
    │
ISP Router
    │
WAN
    │
OPNsense VM
(KVM/QEMU)
    │
LAN
    │
D-Link Switch
    ├── Desktop PC
    ├── Laptop
    ├── MikroTik Access Point
    └── Other Devices
```

## Router Platform

### OPNsense VM

Operating System:

* FreeBSD (OPNsense)

Hosted on:

* Debian Linux
* KVM/QEMU virtualization

Responsibilities:

* Internet routing
* Firewall management
* DHCP services
* DNS forwarding
* Network management

## DHCP

DHCP services are provided by OPNsense using Kea DHCP.

All personal devices receive their network configuration from OPNsense rather than directly from the ISP router.

## Remote Access

Remote access is provided through Tailscale.

This allows secure access to services hosted on EVA without exposing them directly to the public internet.

Services accessible remotely include:

* Nextcloud
* Jellyfin
* Navidrome
* Ollama
* Administrative interfaces

## Network Equipment

### Switch

* 16-port D-Link Gigabit switch

### Wireless

* MikroTik router configured as an access point

## Core Network Services

OPNsense serves as the primary network gateway for my personal network and provides:

* Routing
* Firewall management
* Kea DHCP
* Unbound DNS
* DNS forwarding and caching
* Network policy management

All personal devices receive their network configuration from OPNsense and use Unbound for DNS resolution.


## Design Goals

The network is designed to:

* Learn enterprise networking concepts
* Maintain control over routing and firewall policies
* Provide secure remote access
* Support self-hosted services
* Minimize unnecessary complexity

## Future Improvements

* UPS deployment
* Network monitoring
* VLAN implementation if required
* Additional infrastructure services

```
```
