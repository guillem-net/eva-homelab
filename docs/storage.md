# Storage

## Overview

EVA uses a combination of SAS and SATA storage for performance, redundancy, and backups.

The storage configuration has evolved over time from a single external 1 TB drive attached to an Intel i5-2400M system to a multi-drive setup hosted on enterprise hardware.

## Drive Layout

### System Drive

* SSD
* Debian Linux installation
* Virtual machine storage

### SAS Array

Configuration:

* 2 × 1 TB SAS drives
* RAID 0

Purpose:

* High-performance storage
* Frequently accessed data

### SATA Array

Configuration:

* 2 × 1 TB SATA drives
* RAID 1

Purpose:

* Redundant storage
* Important data

### Backup Drive

Configuration:

* 1 × 4 TB SATA drive

Purpose:

* Local backups
* Recovery storage

## Capacity

Approximate total capacity:

* 8.5 TB raw storage

## Backup Strategy

Custom Bash scripts automatically copy data from both RAID arrays to the dedicated backup drive.

This provides protection against accidental deletion, software failures, and storage issues affecting the primary arrays.

## Lessons Learned

The storage subsystem has provided practical experience with:

* RAID configuration
* SAS hardware
* SATA storage management
* Backup automation
* Capacity planning
* Hardware troubleshooting

One notable hardware incident involved damaging a SAS controller due to an incorrect power connection, requiring replacement and recovery work.
