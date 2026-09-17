# Self-Hosted Linux Infrastructure

**Status:** Operational / actively maintained  
**Checked:** 17 September 2026

## Current platform

- Ubuntu Server **26.04.1 LTS**
- Linux kernel **7.0.0-30-generic**
- x86-64 architecture
- Intel Core i3-7100 @ 3.90 GHz
- 2 physical cores / 4 threads
- Approximately **26 GiB usable memory** reported by the operating system
- Intel VT-x virtualization support

## Storage environment

The server currently manages several SSD/HDD devices serving different roles, including:

- ~447 GB system SSD
- ~256 GB development SSD
- ~466 GB secondary data drives
- ~2.7 TB media/data HDD
- ~1 TB external storage device
- additional removable and legacy storage

The environment uses ext4 and NTFS/FUSE-mounted filesystems, pooled media paths and a mounted cloud-storage remote.

## Current services and tooling

- **Docker Engine 29.8.0**
- OpenSSH server
- Samba SMB daemon
- Ollama local-model service

Docker is installed and managed as part of the environment. No application containers were running during this particular check.

## Administration work

Practical work on the server includes:

- remote Linux administration over SSH
- user and group management
- filesystem ownership and permissions
- Samba shares and authentication
- mounted storage and filesystem management
- Docker/Compose development environments
- WireGuard VPN and routed remote access
- service/process inspection and troubleshooting
- storage benchmarking, migration and cleanup
- multi-user access design
- local AI runtime experimentation

The server is also the base for my automation and security projects, including DevBot, Rae-I and Atlas.