<!-- markdownlint-disable-file MD033 MD041 -->

<h1 align="center">🧪 PNetLab v8</h1>

<h3 align="center">Enterprise Network Virtualization & Emulation Platform</h3>

<p align="center">
  <a href="https://codeberg.org/netkillui/Pnetlabv8"><img src="https://img.shields.io/badge/Upstream%20Release-6.8.84--resolute1-0284c7?style=for-the-badge&logo=codeberg&logoColor=white" alt="Upstream Release"></a>
  <a href="https://ubuntu.com"><img src="https://img.shields.io/badge/Platform-Ubuntu%2026.04%20LTS-e95420?style=for-the-badge&logo=ubuntu&logoColor=white" alt="Ubuntu 26.04 LTS"></a>
  <a href="https://repo.alsyundawy.com/?berkas=PnetLab"><img src="https://img.shields.io/badge/Mirror-repo.alsyundawy.com-238636?style=for-the-badge&logo=server&logoColor=white" alt="High Speed Mirror"></a>
  <a href="https://alsyundawy.com/PNETLab-v8.html"><img src="https://img.shields.io/badge/Hypervisor-Proxmox%20VE%208%2B%20%7C%20VMware-e57000?style=for-the-badge&logo=proxmox&logoColor=white" alt="Proxmox VE 8+"></a>
  <a href="#downloads--artifact-catalogs"><img src="https://img.shields.io/badge/Artifacts-ISO%20%7C%20OVA%20%7C%20DEB%20%7C%20TGZ-8957e5?style=for-the-badge&logo=packagist&logoColor=white" alt="Artifacts"></a>
  <a href="https://codeberg.org/netkillui/Pnetlabv8/issues"><img src="https://img.shields.io/badge/Upstream%20Issues-Codeberg-2185d0?style=for-the-badge&logo=codeberg&logoColor=white" alt="Upstream Issues"></a>
  <a href="https://github.com/alsyundawy/PnetLab-v8"><img src="https://img.shields.io/badge/Maintained%3F-yes-2ea44f?style=for-the-badge&logo=github&logoColor=white" alt="Maintained"></a>
</p>

<p align="center">
  An enterprise-grade, web-based network virtualization and emulation platform for designing, building, and validating complex multi-vendor network topologies (routers, switches, firewalls, and containers) directly in your browser.
</p>

<p align="center">
  <a href="#downloads--artifact-catalogs">
    <img src="https://img.shields.io/badge/🚀_Download_Artifacts-v8.12-238636?style=for-the-badge&logo=cloudsmith&logoColor=white" alt="Download Artifacts">
  </a>
  <a href="https://repo.alsyundawy.com/?berkas=PnetLab">
    <img src="https://img.shields.io/badge/🪞_Dedicated_Mirror-repo.alsyundawy.com-0284c7?style=for-the-badge&logo=server&logoColor=white" alt="Dedicated Mirror">
  </a>
  <a href="https://codeberg.org/netkillui/Pnetlabv8">
    <img src="https://img.shields.io/badge/📦_Upstream_Codeberg-netkillui-blue?style=for-the-badge&logo=codeberg&logoColor=white" alt="Upstream Codeberg">
  </a>
  <a href="https://codeberg.org/netkillui/Pnetlabv8/issues">
    <img src="https://img.shields.io/badge/🐛_Upstream_Issues-Report_Bug-red?style=for-the-badge&logo=codeberg&logoColor=white" alt="Report Upstream Issue">
  </a>
</p>

> Maintained, mirrored, and documented by<br>
> **[`HARRY DERTIN SUTISNA ALSYUNDAWY (@alsyundawy)`](https://github.com/alsyundawy)** —<br>
> Dedicated high-speed download mirror hub, Proxmox VE 8+ deployment architecture, and hardening guide for enterprise network virtualization.
>
> 🪞 **[`Dedicated Mirror (repo.alsyundawy.com)`](https://repo.alsyundawy.com/?berkas=PnetLab)** &nbsp;|&nbsp;
> 📖 **[`Architecture Guide (alsyundawy.com)`](https://alsyundawy.com/PNETLab-v8.html)** &nbsp;|&nbsp;
> 🏠 **[`Upstream Codeberg (@netkillui)`](https://codeberg.org/netkillui/Pnetlabv8)** &nbsp;|&nbsp;
> 🐛 **[`Upstream Issues Tracker`](https://codeberg.org/netkillui/Pnetlabv8/issues)** &nbsp;|&nbsp;
> 💬 **[`Telegram Community`](https://t.me/pnetlab_official)** &nbsp;|&nbsp;
> 💖 **[`Support via PayPal`](https://www.paypal.me/alsyundawy)** &nbsp;|&nbsp;
> 🇮🇩 **[`QRIS Donation`](#support--donation)**

---

## 🧭 Navigation

- [Overview](#overview)
- [Why PNetLab v8? Key Features & Capabilities](#why-pnetlab-v8-key-features--capabilities)
- [System Architecture & Trust Anchors](#system-architecture--trust-anchors)
  - [Execution Flow & Service Topology](#execution-flow--service-topology)
  - [Upstream APT Packages & Cryptographic Signers](#upstream-apt-packages--cryptographic-signers)
- [System Requirements & Sizing Matrix](#system-requirements--sizing-matrix)
- [Downloads & Artifact Catalogs](#downloads--artifact-catalogs)
  - [1. Dedicated High-Speed Mirror (repo.alsyundawy.com)](#1-dedicated-high-speed-mirror-repoalsyundawycom)
  - [2. Official Upstream Release Artifacts (Codeberg & Mega)](#2-official-upstream-release-artifacts-codeberg--mega)
  - [3. Public Community Mirrors](#3-public-community-mirrors)
- [Cryptographic Checksums & Verification](#cryptographic-checksums--verification)
  - [CLI Checksum Verification Commands](#cli-checksum-verification-commands)
- [Installation & Deployment Methods](#installation--deployment-methods)
  - [Method 1: Automated Network Installer (Ubuntu 26.04)](#method-1-automated-network-installer-ubuntu-2604)
  - [Method 2: Proxmox VE 8+ Enterprise Deployment](#method-2-proxmox-ve-8-enterprise-deployment)
  - [Method 3: Bare-Metal Server Installation via Full ISO](#method-3-bare-metal-server-installation-via-full-iso)
  - [Method 4: Air-Gapped Offline Bundle Deployment](#method-4-air-gapped-offline-bundle-deployment)
- [Critical Production Caveats & Troubleshooting](#critical-production-caveats--troubleshooting)
  - [⚠️ Strict Prohibition: No Upgrade Path from Legacy v4, v5, or v6](#️-strict-prohibition-no-upgrade-path-from-legacy-v4-v5-or-v6)
  - [1. Preflight Error: Installer Refuses /etc/network/interfaces](#1-preflight-error-installer-refuses-etcnetworkinterfaces)
  - [2. APT Simulation Error: Held Packages Block Mutation](#2-apt-simulation-error-held-packages-block-mutation)
  - [3. Guacamole Console Restart-Loop Issue (#19 & #35)](#3-guacamole-console-restart-loop-issue-19--35)
  - [4. Retired Systemd Store Units Cleanup](#4-retired-systemd-store-units-cleanup)
  - [5. UFW Firewall Removed: Switch to iptables-persistent](#5-ufw-firewall-removed-switch-to-iptables-persistent)
- [Post-Installation & Runtime Validation Checklist](#post-installation--runtime-validation-checklist)
- [Upstream Credits & Attribution](#upstream-credits--attribution)
- [Issues & Bug Reports Protocol](#issues--bug-reports-protocol)
- [Maintainer & Contact](#maintainer--contact)
- [Support & Donation](#support--donation)
- [License](#license)

---

## Overview

**PNetLab v8** (Packet Network Lab) is an advanced, self-hosted network emulation platform designed specifically for modern Linux hosts running **Ubuntu 26.04 LTS ("27H1 Resolute")** with mandatory KVM hardware virtualization (`/dev/kvm`). Built to empower network architects, security researchers, certification candidates (CCNA, CCNP, CCIE, JNCIE), and DevOps practitioners, PNetLab v8 allows operators to run high-density topologies combining virtual routers, switches, firewalls, servers, and containerized workloads inside a responsive, clientless web interface.

This repository serves as a community landing page, high-speed download mirror hub, and deployment hardening guide. It does **not** host the proprietary application source code.

All upstream package releases, signed manifests, and core APT channels are maintained by **[@netkillui](https://codeberg.org/netkillui)** on Codeberg. The signed upstream network installer channel serves release `6.8.84resolute1`, addressing critical fixes including the Guacamole console key startup race condition ([#19](https://codeberg.org/netkillui/Pnetlabv8/issues/19), [#35](https://codeberg.org/netkillui/Pnetlabv8/issues/35)).

---

## Why PNetLab v8? Key Features & Capabilities

| Capability                           | Technical Implementation                                                                                                    | Enterprise Benefit                                                                                                                     |
| :----------------------------------- | :-------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------- |
| **Clientless HTML5 Web Console**     | Integrated Apache Guacamole daemon (`pnet-guac-lite` on port `8081`) with native WebSocket terminal streaming.              | Eliminates desktop client requirements (SecureCRT/PuTTY/VNC); access any node console directly in Chrome, Firefox, or Safari.          |
| **Multi-Engine Virtualization**      | Concurrently bridges QEMU/KVM VMs, Cisco IOL (IOS on Linux), Dynamips, VPCS, and native Docker containers.                  | Design heterogeneous multi-vendor networks (Cisco, Juniper, Arista, Fortinet, Linux) inside one unified visual canvas.                 |
| **Modern Kernel Optimization**       | Tuned for Linux 6.8+ kernels on Ubuntu 26.04 Resolute with nested virtualization (`/dev/kvm`) and soft-RoCE (`rdma_rxe`).   | Near bare-metal CPU execution speeds, hardware-assisted nested hypervisors, and high-throughput low-latency packet switching.          |
| **Automated Lifecycle & Updates**    | Built-in upstream updater utility `sudo pnetlab-update` streaming signed release channels (`6.8.84-resolute1`).             | Safe, one-command in-place patching of web frontends, wrappers, and core broker daemons without topology disruption.                   |
| **Proxmox VE 8+ Tuning**             | Custom `qm create` deployment profile with `virtio-scsi-single`, TRIM `discard=on`, `ssd=1`, `iothread=1`, and `balloon=0`. | Zero disk space bloat from temporary lab images, immune to QEMU memory balloon thrashing, and enterprise NVMe I/O throughput.          |
| **Air-Gapped & Offline Portability** | Full standalone bootable ISO (`.iso`) and compressed offline tarball bundles (`.tgz`) with pinned deb repositories.         | 100% operational in isolated enterprise datacenters, secure defense labs, and restricted networks with zero external WAN connectivity. |

---

## System Architecture & Trust Anchors

### Execution Flow & Service Topology

```mermaid
flowchart TB
    subgraph ClientLayer["Client Access Layer"]
        Browser["Modern Web Browser<br/>(Chrome / Safari / Firefox / Edge)"]
    end

    subgraph PresentationLayer["PNetLab v8 Web Services (Port 80 / 443 / 8081)"]
        Apache["Apache2 Web Server<br/>(PHP 8.5-FPM Runtimes)"]
        Guac["pnet-guac-lite Micro-Daemon<br/>(Guacamole HTML5 Terminal :8081)"]
    end

    subgraph CoreLayer["Orchestration & Bridge Control"]
        Broker["pnetlab-brokerd Daemon<br/>(Topology & API Controller :8025)"]
        LinuxBridge["Host Linux Kernel & Network Bridges<br/>(pnet0: Management | pnet1-9: Lab Interconnects | nat0: Outbound)"]
    end

    subgraph NodeLayer["Multi-Engine Virtualization Runtimes"]
        QEMU["QEMU / KVM Nodes<br/>(CSR1000v, vQFX, vEOS, FortiGate)"]
        IOL["Cisco IOL Runtimes<br/>(IOS on Linux L2 / L3)"]
        Docker["Docker Containers<br/>(Ubuntu, Alpine, Network Tools)"]
        VPCS["VPCS Simulator<br/>(Lightweight Test Endpoints)"]
    end

    Browser -->|HTTP / HTTPS REST API| Apache
    Browser -->|WebSocket Console Stream :8081| Guac
    Apache -->|IPC & Control Commands :8025| Broker
    Broker -->|Bridge Orchestration| LinuxBridge
    Guac -->|Telnet / SSH / VNC / RDP| LinuxBridge
    LinuxBridge --> QEMU
    LinuxBridge --> IOL
    LinuxBridge --> Docker
    LinuxBridge --> VPCS
```

```text
                       ┌──────────────────────────────────────────────┐
                       │           PNETLab v8 Web Frontend            │
                       │           (Apache2 / PHP 8.5-FPM)            │
                       └──────────────────────┬───────────────────────┘
                                              │
                      ┌───────────────────────┴───────────────────────┐
                      ▼                                               ▼
         ┌─────────────────────────┐                     ┌─────────────────────────┐
         │   Core Broker Service   │                     │   HTML5 Web Console     │
         │  pnetlab-brokerd :8025  │                     │   pnet-guac-lite :8081  │
         └────────────┬────────────┘                     └────────────┬────────────┘
                      │                                               │
         ┌────────────┴───────────────────────────────────────────────┴────────────┐
         │                   Host Linux Kernel & Networking Bridge                 │
         │          pnet0 (mgmt / eth0)  │  pnet1 .. pnet9 (lab)  │  nat0          │
         └────────────────────────────────────┬────────────────────────────────────┘
                                              │
         ┌────────────────────────────────────┴────────────────────────────────────┐
         │                     Virtualized Node Runtimes                           │
         │      QEMU / KVM Nodes   │   Cisco IOL   │   Docker   │   VPCS           │
         └─────────────────────────────────────────────────────────────────────────┘
```

### Upstream APT Packages & Cryptographic Signers

PNetLab v8 depends on a suite of manifest-pinned Debian packages:

| Package Name                       | Functional Responsibility                                                           |
| :--------------------------------- | :---------------------------------------------------------------------------------- |
| `pnetlab`                          | Core web canvas, UI components, REST API routing, and lab orchestration services.   |
| `pnetlab-docker`                   | Containerized node driver, image management, and topology bridge integration.       |
| `pnetlab-guacd` & `pnet-guac-lite` | Clientless HTML5 terminal and desktop gateway (Guacamole protocol micro-daemon).    |
| `pnetlab-qemu`                     | Accelerated KVM hypervisor integration, disk wrapper scripts, and hardware flags.   |
| `pnetlab-schema`                   | Database schema migrations, MySQL/MariaDB table setup, and topology validation.     |
| `pnetlab-vpcs`                     | Lightweight Virtual PC Simulator integration for fast ping/traceroute verification. |
| `pnetlab-bridge-dkms`              | Kernel module for multi-bridge network interfaces and raw frame forwarding.         |

**Official Cryptographic Trust Anchors:**

- **Offline Manifest Signer Fingerprint**: `158D99DF8D57040AA8E0EDA58F353DF9007A2BB4`
- **APT Repository Signing Key Fingerprint**: `EA21DC771565BC84C57A610861756807AC7005EC`

---

## System Requirements & Sizing Matrix

| Resource               | Minimum (Evaluation / Light Labs)      | Recommended (Standard Multi-Vendor Labs)                  | Production (High-Density Topologies)                 |
| :--------------------- | :------------------------------------- | :-------------------------------------------------------- | :--------------------------------------------------- |
| **CPU Architecture**   | 64-bit x86_64 with Intel VT-x or AMD-V | 8–16 physical cores with nested virtualization            | 24–64+ physical cores (dual-socket Xeon / EPYC)      |
| **Memory (RAM)**       | 8 GB RAM                               | 32 GB – 64 GB RAM                                         | 128 GB – 512 GB+ ECC Registered RAM                  |
| **Disk Storage**       | 40 GB available disk space             | 250 GB – 500 GB NVMe SSD                                  | 1 TB – 4 TB+ PCIe 4.0/5.0 NVMe (high sustained IOPS) |
| **Host OS**            | Ubuntu 26.04 LTS ("27H1 Resolute")     | Clean server installation without third-party web servers | Bare-metal Ubuntu 26.04 or Proxmox VE 8+ VM          |
| **Hypervisor Support** | VMware Workstation 17+ / Fusion        | Proxmox VE 8.0–8.4+ / ESXi 7.0–8.0+                       | Proxmox VE 8+ with VirtIO SCSI Single TRIM/discard   |
| **Network Interface**  | 1x Gigabit NIC (Bridged / Static IPv4) | Dedicated management NIC + 802.1Q trunking                | Dual 10G/25G SFP+ bonded interfaces (`bond0`)        |

> [!IMPORTANT]
> **Nested Virtualization Mandatory:** If hosting PNetLab inside a virtual machine (VMware or Proxmox VE), nested virtualization **must** be active on the hypervisor CPU configuration. Verify with `grep -E 'vmx|svm' /proc/cpuinfo` inside the host.

---

## Downloads & Artifact Catalogs

### 1. Dedicated High-Speed Mirror ([repo.alsyundawy.com](https://repo.alsyundawy.com/?berkas=PnetLab))

Direct download links hosted on high-bandwidth infrastructure with resumable transfers (`curl -C -` / `wget -c`) and no download limits:

| Artifact                            | Format | Description                                                                      | Direct Mirror Link                                                                                       |
| :---------------------------------- | :----: | :------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------- |
| **PNetLab Netinstall Appliance**    | `.ova` | Minimal Ubuntu 27H1 appliance with automated online bootstrapping.               | [Download Netinstall OVA](https://repo.alsyundawy.com/PnetLab/PNetLab-27H1-v8-netinstall.ova)            |
| **PNetLab Full Bootable ISO v8.12** | `.iso` | Standalone ISO installer for physical bare-metal servers and offline VMs.        | [Download Full ISO](https://repo.alsyundawy.com/PnetLab/PNetLab-27H1-v8.12.iso)                          |
| **PNetLab Full Turn-Key OVA v8.12** | `.ova` | Complete, pre-packaged virtual appliance with v8.12 ready to run out of the box. | [Download Full OVA](https://repo.alsyundawy.com/PnetLab/PNetLab-27H1-v8.12.ova)                          |
| **Offline Update Bundle 6.8.62**    | `.tgz` | Offline tarball bundle for air-gapped host updates without internet access.      | [Download Bundle TGZ](https://repo.alsyundawy.com/PnetLab/pnetlab-27H1-v8.62-6.8.62-resolute-bundle.tgz) |

### 2. Official Upstream Release Artifacts (Codeberg & Mega)

| Artifact                   | Target Environment                  | Upstream Link                                                                                                                          |
| :------------------------- | :---------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------- |
| **Network Install Script** | Fresh Ubuntu 26.04 LTS host         | [Download Script](https://codeberg.org/api/packages/netkillui/generic/pnetlab-core-assets/0.channel/pnetlab-network-install-latest.sh) |
| **OVA (Autoinstaller)**    | VMware / VirtualBox unattended boot | [Download via Mega](https://mega.nz/file/uNAz3JDb#CQA93KkaU3XrCs6EIosChOjYonn1W4ELgnLm7NcZ2Wg)                                         |
| **Desktop Install Bundle** | Bare-metal Ubuntu / Xubuntu Desktop | [Download via Mega](https://mega.nz/file/HAg22B6J#AwXunC9XMMZuhkbf5_p4E1lkrSlPVrCVnVIJmbFV26Q)                                         |
| **Custom Lab Images Pack** | AP, Client, OpenBMP, Soft-RoCE RXE  | [Download via Mega](https://mega.nz/folder/3dQ3SIhL#MX518yID5GuuLUkDbCRa0g)                                                            |

### 3. Public Community Mirrors

| Mirror Name                                | Mirror Type           | Link                                                   |
| :----------------------------------------- | :-------------------- | :----------------------------------------------------- |
| **MediaFire (PNetLab-v8.2-6.8.84.ova)**    | Cloud Mirror          | <https://www.mediafire.com/file/uy10drloalz61a5>       |
| **PixelDrain (PNetLab-v8.2-6.8.84.ova)**   | High-Speed CDN        | <https://pixeldrain.com/u/3WTSKNcY>                    |
| **MediaFire (PNetLab-v8-netinstall.ova)**  | Cloud Mirror          | <https://www.mediafire.com/file/txzfx3rgwy2q3r6>       |
| **PixelDrain (PNetLab-v8-netinstall.ova)** | High-Speed CDN        | <https://pixeldrain.com/u/kSq9bXqq>                    |
| **Telegram Community Channel**             | Releases & Discussion | [t.me/pnetlab_official](https://t.me/pnetlab_official) |

---

## Cryptographic Checksums & Verification

Always verify SHA-256 hashes prior to importing or booting images to guarantee file integrity:

| Artifact Filename           | Format | Primary Checksum (SHA-256)                                         |
| :-------------------------- | :----: | :----------------------------------------------------------------- |
| `PNetLab-v8.2-6.8.84.ova`   |  OVA   | `855da18ff00318f08eea373f029cba579865f3a93f0bbfe8eb0767296e8f8e19` |
| `PNetLab-v8-netinstall.ova` |  OVA   | `7760ef1fc5c9600fa8e4befd939773163e0676c8a8001a04394fc45dd7536822` |

### CLI Checksum Verification Commands

#### On Linux

```bash
sha256sum PNetLab-v8.2-6.8.84.ova
sha256sum PNetLab-v8-netinstall.ova
```

#### On macOS

```bash
shasum -a 256 PNetLab-v8.2-6.8.84.ova
shasum -a 256 PNetLab-v8-netinstall.ova
```

#### On Windows (PowerShell)

```powershell
Get-FileHash .\PNetLab-v8.2-6.8.84.ova -Algorithm SHA256
Get-FileHash .\PNetLab-v8-netinstall.ova -Algorithm SHA256
```

---

## Installation & Deployment Methods

### Method 1: Automated Network Installer (Ubuntu 26.04)

Recommended for clean bare-metal servers or cloud instances:

```bash
# 1. Update host base system
sudo apt update && sudo apt full-upgrade -y

# 2. Execute upstream manifest-driven network installer
curl -fsSL https://codeberg.org/api/packages/netkillui/generic/pnetlab-core-assets/0.channel/pnetlab-network-install-latest.sh | sudo bash -s -- --yes --release latest
```

---

### Method 2: Proxmox VE 8+ Enterprise Deployment

Proxmox VE 8.0–8.4+ (Debian 12 Bookworm with Kernel 6.5/6.8+) provides an optimal production environment. Follow these production CLI steps:

#### Step 1: Ensure Host KVM Nested Virtualization

```bash
# For Intel CPUs (Expected output: Y or 1)
cat /sys/module/kvm_intel/parameters/nested
# If output is N, enable permanently:
echo "options kvm-intel nested=Y" | sudo tee /etc/modprobe.d/kvm-intel.conf
sudo modprobe -r kvm_intel && sudo modprobe kvm_intel

# For AMD CPUs (Expected output: 1)
cat /sys/module/kvm_amd/parameters/nested
# If output is 0, enable permanently:
echo "options kvm-amd nested=1" | sudo tee /etc/modprobe.d/kvm-amd.conf
sudo modprobe -r kvm_amd && sudo modprobe kvm_amd
```

#### Step 2: Download Appliance & Unpack OVA on PVE Host

```bash
cd /var/lib/vz/dump || cd /tmp
wget -c https://repo.alsyundawy.com/PnetLab/PNetLab-27H1-v8.12.ova
tar -xvf PNetLab-27H1-v8.12.ova
```

#### Step 3: Create Hardware-Tuned VM Profile

```bash
# Create VM ID 800 with enterprise flags:
# - CPU: host (passes nested virtualization flags)
# - Ballooning: 0 (DISABLED - prevents severe QEMU node memory thrashing)
# - Controller: virtio-scsi-single with TRIM discard & iothread
# - Firewall: 0 (disabled on bridge to allow transparent lab traffic)
qm create 800 --name "PNETLab-v8-Enterprise" \
  --ostype l26 \
  --cpu host \
  --cores 8 \
  --sockets 1 \
  --numa 0 \
  --memory 16384 \
  --balloon 0 \
  --scsihw virtio-scsi-single \
  --net0 virtio,bridge=vmbr0,firewall=0 \
  --agent 1 \
  --machine q35 \
  --onboot 1

# Import VMDK disk to storage pool (local-lvm or local-zfs)
qm importdisk 800 *.vmdk local-lvm --format qcow2

# Attach disk as SCSI0 with SSD discard optimization
qm set 800 --scsi0 local-lvm:vm-800-disk-0,discard=on,ssd=1,iothread=1
qm set 800 --boot order=scsi0
qm start 800
```

---

### Method 3: Bare-Metal Server Installation via Full ISO

For air-gapped physical servers or dedicated bare-metal workstations:

1. Download `PNetLab-27H1-v8.12.iso` from the [Dedicated Mirror](https://repo.alsyundawy.com/?berkas=PnetLab).
2. Write the ISO to a USB flash drive using [Ventoy](https://www.ventoy.net) or `dd`:

   ```bash
   sudo dd if=PNetLab-27H1-v8.12.iso of=/dev/sdX bs=4M status=progress conv=fsync
   ```

3. Boot the physical machine from the USB drive.
4. Follow the automatic installer prompts to partition disk storage and configure initial network parameters.
5. Reboot the server, remove the boot drive, and access `https://<server-ip>/`.

---

### Method 4: Air-Gapped Offline Bundle Deployment

For isolated environments with zero internet access:

```bash
# 1. Download offline tarball bundle
wget -c https://repo.alsyundawy.com/PnetLab/pnetlab-27H1-v8.62-6.8.62-resolute-bundle.tgz

# 2. Extract into staging directory
mkdir -p /root/pnetlab-bundle-staging
sudo tar -xzvf pnetlab-27H1-v8.62-6.8.62-resolute-bundle.tgz -C /root/pnetlab-bundle-staging
cd /root/pnetlab-bundle-staging

# 3. Install packages in-place
if [ -f "./install.sh" ]; then
  sudo bash ./install.sh
elif [ -f "./update.sh" ]; then
  sudo bash ./update.sh
else
  sudo dpkg -i *.deb || sudo apt-get -f install -y
fi

# 4. Correct UNetLab filesystem permissions
sudo /opt/unetlab/wrappers/unl_wrapper -a fixpermissions
```

---

## Critical Production Caveats & Troubleshooting

### ⚠️ Strict Prohibition: No Upgrade Path from Legacy v4, v5, or v6

> [!CAUTION]
> **DO NOT ATTEMPT TO UPGRADE FROM LEGACY PNETLAB v4/v5/v6!**
> There is **no valid upgrade path** from legacy releases (Ubuntu 18.04 / 20.04) to PNetLab v8 (Ubuntu 26.04). The underlying database architecture, Apache Guacamole daemon, PHP 8.5-FPM stack, and systemd units have been completely redesigned. Attempting an in-place upgrade will irreparably destroy your operating system. Back up node images and lab configs, then perform a clean installation.

---

### 1. Preflight Error: Installer Refuses `/etc/network/interfaces`

- **Symptom:** The network installer stops with:
  `ERROR: preflight Check A refuses administrator content in /etc/network/interfaces; use --no-cloud-uplink`
- **Root Cause:** PNetLab's installer prevents accidental destruction of pre-configured network bridges on existing servers.
- **Solution:** Re-run the installer with the `--no-cloud-uplink` parameter to preserve your interfaces:

  ```bash
  curl -fsSL https://codeberg.org/api/packages/netkillui/generic/pnetlab-core-assets/0.channel/pnetlab-network-install-latest.sh | sudo bash -s -- --yes --release latest --no-cloud-uplink
  ```

---

### 2. APT Simulation Error: Held Packages Block Mutation

- **Symptom:** Preflight aborts with:
  `The following held packages will be changed: pnetlab-docker pnetlab-guacd ... E: Held packages were changed and -y was used without --allow-change-held-packages`
- **Solution:** Temporarily release the hold on PNetLab packages prior to installation:

  ```bash
  sudo apt-mark unhold pnetlab pnetlab-docker pnetlab-guacd pnetlab-qemu pnetlab-schema
  ```

---

### 3. Guacamole Console Restart-Loop Issue ([#19](https://codeberg.org/netkillui/Pnetlabv8/issues/19) & [#35](https://codeberg.org/netkillui/Pnetlabv8/issues/35))

- **Symptom:** Installation fails during socket verification:
  `ERROR: pnet-guac-lite.service restart-loop evidence: NRestarts=45`
- **Root Cause:** The `pnet-guac-lite` daemon starts before `/etc/pnet-webconsole/guac.env` (`GUAC_CRYPT_KEY`) is initialized.
- **Workaround:** Generate the cryptographic key manually and restart the service:

  ```bash
  # Create key directory and generate 32-byte base64 encryption key
  sudo install -d -m 0755 /etc/pnet-webconsole
  if [ ! -s /etc/pnet-webconsole/guac.env ]; then
    GUAC_KEY=$(head -c 24 /dev/urandom | base64 | tr -d ' ')
    printf 'GUAC_CRYPT_KEY=%s\n' "$GUAC_KEY" | sudo tee /etc/pnet-webconsole/guac.env >/dev/null
    sudo chmod 0600 /etc/pnet-webconsole/guac.env
  fi

  # Reset systemd failure counters and restart services
  sudo systemctl daemon-reload
  sudo systemctl reset-failed pnet-guac-lite.service guacd.service
  sudo systemctl restart guacd.service pnet-guac-lite.service

  # Verify socket is active
  sudo ss -ltnH 'sport = :8081'
  ```

---

### 4. Retired Systemd Store Units Cleanup

- **Symptom:** `systemctl --failed` displays failures for `harddisk_limit.service`, `mysql_recovery.service`, or `process_limit.service`.
- **Root Cause:** These legacy units target `/opt/unetlab/html/store/`, which was retired in modern v8 builds.
- **Solution:** Safely disable and clear these retired units without deleting package-tracked files:

  ```bash
  sudo systemctl disable --now harddisk_limit.service mysql_recovery.service process_limit.service
  sudo systemctl reset-failed harddisk_limit.service mysql_recovery.service process_limit.service
  ```

---

### 5. UFW Firewall Removed: Switch to `iptables-persistent`

- **Symptom:** UFW is uninstalled during package installation and replaced with `iptables-persistent`.
- **Warning for Remote Admins:** Save firewall rules before running the installer so SSH access remains open:

  ```bash
  sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT
  sudo iptables -A INPUT -p tcp --dport 80 -j ACCEPT
  sudo iptables -A INPUT -p tcp --dport 443 -j ACCEPT
  sudo netfilter-persistent save
  ```

---

## Post-Installation & Runtime Validation Checklist

Verify your PNetLab v8 runtime health using this operational checklist:

```bash
# 1. Verify installed package versions
dpkg -l 'pnetlab*' | awk '/^ii/'

# 2. Check for failed systemd services
systemctl --failed

# 3. Confirm active core daemons
systemctl is-active mysql docker php8.5-fpm pnetlab-brokerd pnet-guac-lite

# 4. Validate network bridge creation
ip -br link | grep -E 'pnet|nat0'

# 5. Check listening sockets
sudo ss -lntp | grep -E ':80|:443|:22|:8081|:8025'

# 6. Verify hardware virtualization
kvm-ok

# 7. Apply standard UNetLab filesystem permissions
sudo /opt/unetlab/wrappers/unl_wrapper -a fixpermissions
```

---

## Upstream Credits & Attribution

This repository is maintained as an independent distribution mirror, download repository, and enterprise documentation reference. All development, packaging, and source releases are maintained by the upstream author:

| Component                                | Resource                                                                                                  | Description                                                 |
| :--------------------------------------- | :-------------------------------------------------------------------------------------------------------- | :---------------------------------------------------------- |
| 🏠 **Original Upstream Repository**      | [codeberg.org/netkillui/Pnetlabv8](https://codeberg.org/netkillui/Pnetlabv8)                              | Official source of releases, issue tracker, and core assets |
| 👤 **Original Contributor & Maintainer** | [@netkillui](https://codeberg.org/netkillui)                                                              | Core platform development and release engineering           |
| 📦 **Official Package Channel**          | [pnetlab-core-assets](https://codeberg.org/api/packages/netkillui/generic/pnetlab-core-assets/0.channel/) | Upstream Debian package distribution channel                |
| 🪞 **Dedicated Cloud Mirror**            | [repo.alsyundawy.com/?berkas=PnetLab](https://repo.alsyundawy.com/?berkas=PnetLab)                        | High-speed cloud mirror for ISO, OVA, and TGZ bundles       |
| 📖 **Deployment Architecture Reference** | [alsyundawy.com/PNETLab-v8.html](https://alsyundawy.com/PNETLab-v8.html)                                  | Comprehensive engineering guide by Harry Dertin Sutisna     |

---

## Issues & Bug Reports Protocol

> [!IMPORTANT]
> **Bug Reporting Protocol:**
> This repository is a distribution mirror and verification hub. We do **not** maintain the application codebase.
>
> If you encounter bugs, feature requests, or daemon anomalies, please report them directly to the upstream issue tracker:
>
> 👉 **[Submit an Issue on Codeberg (netkillui/Pnetlabv8)](https://codeberg.org/netkillui/Pnetlabv8/issues)**
>
> Please review existing resolved issues (e.g., [#19](https://codeberg.org/netkillui/Pnetlabv8/issues/19) and [#35](https://codeberg.org/netkillui/Pnetlabv8/issues/35)) before opening new reports.

---

## Maintainer & Contact

### Harry Dertin Sutisna Alsyundawy (@alsyundawy)

- 🌐 Website: [https://www.alsyundawy.com](https://www.alsyundawy.com)
- 💻 GitHub: [@alsyundawy](https://github.com/alsyundawy)
- 🐦 Twitter / X: [@alsyundawy](https://x.com/alsyundawy)
- 🏢 Organization: [WWW.ALSYUNDAWY.NET](https://www.alsyundawy.net)
- 📍 Location: DKI Jakarta, Indonesia

---

## Support & Donation

If this documentation, mirror hub, and deployment scripts are helpful for your lab infrastructure, you can support continuous maintenance here:

- **PayPal**: [`https://www.paypal.me/alsyundawy`](https://www.paypal.me/alsyundawy)

### 🇮🇩 QRIS (Quick Response Code Indonesian Standard)

Scan the QRIS barcode below using any Indonesian mobile banking app (BCA, Mandiri, BRI, BNI, BSI, CIMB Niaga, Permata) or e-wallet (GoPay, OVO, DANA, LinkAja, ShopeePay):

![QRIS Donation Barcode - ALSYUNDAWY](https://github.com/user-attachments/assets/a0126f28-6dde-43da-ba14-d7c9a27de0df)

- **Merchant / Account Name**: **ALSYUNDAWY IT SOLUTION**
- **NMID**: **`ID1020021153676`**
- **Direct Barcode Asset Link**: [`https://github.com/user-attachments/assets/a0126f28-6dde-43da-ba14-d7c9a27de0df`](https://github.com/user-attachments/assets/a0126f28-6dde-43da-ba14-d7c9a27de0df)
- **WhatsApp Confirmation**: [`+62 856-8515-212`](https://wa.me/628568515212)

---

## License

This documentation and repository mirror guide are provided for community educational and network engineering purposes. PNetLab software packages, binaries, and wrappers are subject to upstream licensing terms from **[@netkillui](https://codeberg.org/netkillui)**. All registered trademarks, logos, and vendor names (Cisco, Juniper, Arista, Proxmox, VMware, Ubuntu) belong to their respective copyright holders.
