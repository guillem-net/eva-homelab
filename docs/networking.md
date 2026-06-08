# Networking

## Overview

EVA serves as the central infrastructure node of my home network.

The server hosts an OPNsense virtual machine that acts as the primary router and firewall for the network. Traffic enters through a dedicated WAN interface and is routed to the local network through a separate LAN interface.

Remote access is provided through Tailscale, allowing secure access to internal services without exposing them directly to the internet.

## Network Topology


Internet
    │
ISP Router
    │
 NIC1 (WAN)
    │
+-----------+
|    EVA    |
+-----------+
    │
 NIC2 (LAN)
    │
OPNsense VM
    │
Network Switch
   ├── MikroTik Access Point
   └── Ethernet Devices


## Hardware

### Switch

* 16-port D-Link Gigabit switch

### Wireless

* MikroTik router configured as an access point

## Routing

Routing and firewall functions are handled by OPNsense running as a virtual machine under KVM/QEMU.

### OPNsense VM

Operating System:

* FreeBSD (OPNsense)

Responsibilities:

* Routing
* Firewall management
* DHCP
* Network segmentation
* Gateway management

## Remote Access

Remote connectivity is provided using Tailscale.

Benefits:

* Secure encrypted access
* No public service exposure required
* Access to internal services from external networks

## Design Goals

The networking design focuses on:

* Security
* Simplicity
* Learning enterprise networking concepts
* Self-hosted infrastructure management

## Future Improvements

Planned upgrades include:

* UPS integration
* VLAN implementation
* Monitoring and alerting
* Additional network segmentation
* Redundant backup infrastructure

```
```
