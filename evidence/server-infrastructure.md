# Self-Hosted Linux Infrastructure — Verified Evidence

**Status:** Operational / actively maintained  
**Verification date:** 17 September 2026  
**Evidence source:** Live read-only inspection of the self-hosted server environment. Sensitive identifiers and network details are intentionally omitted.

## Current platform

- Ubuntu Server **26.04.1 LTS**
- Linux kernel **7.0.0-30-generic**
- x86-64 architecture
- Intel Core i3-7100 @ 3.90 GHz
- 2 physical cores / 4 threads
- Approximately **26 GiB usable memory** reported by the operating system
- Hardware virtualization support (Intel VT-x)

## Storage environment

The server currently manages several SSD/HDD devices serving different roles, including:

- ~447 GB system SSD
- ~256 GB development SSD
- ~466 GB secondary data drives
- ~2.7 TB media/data HDD
- ~1 TB external storage device
- Additional mounted removable/legacy storage

The storage environment includes ext4, NTFS/FUSE-mounted filesystems, pooled media paths and a mounted cloud-storage remote. Public evidence intentionally omits device serials, UUIDs and internal path details that are not needed to demonstrate the work.

## Current services and tooling

Verified installed/running service layer includes:

- **Docker Engine 29.8.0**
- Docker system service
- OpenSSH server
- Samba SMB daemon
- Ollama local-model service

Docker is installed and managed as part of the environment. At the time of this verification snapshot, no application containers were running, so this page does not claim that historical containers were currently active.

## Administration work demonstrated

Practical work on this environment includes:

- Remote Linux administration over SSH
- User and group management
- Filesystem ownership and permissions
- Samba authentication and network shares
- Mounted storage and filesystem management
- Docker/Compose application environments
- VPN and routed remote-access work using WireGuard
- Service/process inspection and troubleshooting
- Storage benchmarking, migration and cleanup
- Multi-user privacy and access-boundary redesign
- Local AI runtime experimentation

## Development environment

A dedicated development project root currently contains multiple structured projects, including application work with separate backend, frontend and mobile areas.

One active application project contains:

- Java backend using **Java 21**
- **Spring Boot 3.3.x**
- Maven build configuration
- Docker Compose development definition
- Flutter mobile application structure
- Android, iOS, Linux, macOS, Windows and web target scaffolding
- Automated test files and project documentation
- Generated review/report evidence from development automation workflows

## Security and publication policy

This public evidence is deliberately sanitised. It does **not** publish:

- credentials or `.env` values
- private keys
- internal or public IP addresses
- MAC addresses
- machine or boot identifiers
- user account lists
- secrets
- unnecessary network topology details

The goal is to demonstrate practical infrastructure experience without turning the portfolio into an infrastructure disclosure document.
