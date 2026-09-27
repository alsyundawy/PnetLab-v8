# PNetLab v8 6.8.84

PNetLab is a self-hosted network emulation platform for building and running
virtual labs (routers, switches, firewalls, servers, and more) in your browser.

This repository is a landing page for **PNetLab v8** downloads and upgrade
instructions. It does not host the application source.

The signed network-install channel serves `6.8.84resolute1`. This release fixes
the fresh-install Guac key startup race reported in [#35](https://codeberg.org/netkillui/Pnetlabv8/issues/35)
and [#19](https://codeberg.org/netkillui/Pnetlabv8/issues/19).

## Downloads

| Artifact | Description | Link |
| --- | --- | --- |
| Network Install Script | Hands-off installer for a fresh Ubuntu 26.04 (27H1 "Resolute") host — pulls and installs the latest PNetLab v8 release over the network. | [download](https://codeberg.org/api/packages/netkillui/generic/pnetlab-core-assets/0.channel/pnetlab-network-install-latest.sh) |
| OVA (autoinstaller) | Minimal Ubuntu 26.04 image with an unattended autoinstaller — boots and installs PNetLab v8 itself. | [download](https://mega.nz/file/uNAz3JDb#CQA93KkaU3XrCs6EIosChOjYonn1W4ELgnLm7NcZ2Wg) |
| Desktop Install Bundle | Installs PNetLab v8 on Ubuntu Desktop workstation environment on bare metal. Tested on Ubuntu 26.04 Desktop and Xubuntu 26.04 Desktop — Xubuntu is recommended for its lighter resource footprint. Dual boot alongside Widows or external SSD setup works. | [download](https://mega.nz/file/HAg22B6J#AwXunC9XMMZuhkbf5_p4E1lkrSlPVrCVnVIJmbFV26Q) |
| Custom Images | Lab images for wifi access point, client, OpenBMP, and ROCEv2 client with RXE configured. | [download](https://mega.nz/folder/3dQ3SIhL#MX518yID5GuuLUkDbCRa0g) |

## Requirements

- 64-bit host, hardware virtualization support (Intel VT-x / AMD-V)
- Minimum 4 vCPU / 8 GB RAM / 40 GB disk for light use; scale up for larger labs
- Ubuntu 26.04 LTS ("27H1 Resolute") for the network install method

## Installation

### Option 1 — Network install (recommended)

Run the network install script on a fresh Ubuntu 26.04 server:

```bash
curl -fsSL https://codeberg.org/api/packages/netkillui/generic/pnetlab-core-assets/0.channel/pnetlab-network-install-latest.sh | sudo bash -s -- --yes --release latest
```

The script partitions storage, installs dependencies, and pulls the latest
PNetLab v8 package automatically.

### Option 2 — OVA (autoinstaller)

1. Download the OVA from the table above.
2. Import it into VMware Workstation/ESXi or VirtualBox.
3. Power on the VM. It boots into an unattended autoinstaller that partitions
  the disk and installs Ubuntu 26.04 + PNetLab v8 with no manual input beyond
  DHCP/static IP choice.
4. Once the install finishes and the VM reboots, log in to the web UI at
  `https://<host-ip>/`.

## Updating

PNetLab v8 ships update packages through its built-in update mechanism.

```bash
sudo pnetlab-update
```

This checks the configured release channel, downloads the newest package, and
applies it in place. Review the changelog before updating a production lab
host.

### Manual upgrade (if `pnetlab-update` is unavailable)

1. Back up `/opt/unetlab` (or your configured lab data path) and any custom
  node images.
2. Download the target release package (placeholder link above).
3. Install it:
  
  ```bash
  sudo dpkg -i pnetlab_<version>_amd64.deb
  sudo apt-get -f install
  ```
  
4. Reboot and verify the web UI and running labs come back up correctly.

## Support / Issues

Open an issue in this repository's issue tracker.

## License

See the license terms distributed with the PNetLab v8 package.



# PNetLab v8 — Virtual Appliance Collection

> **PNetLab Virtual Appliance & NetInstall**
>
> Koleksi image PNetLab dalam format **OVA** untuk deployment pada platform virtualisasi seperti VMware, Proxmox VE, VirtualBox, maupun hypervisor lain yang mendukung import OVA.

PNetLab merupakan platform network emulation yang menyediakan lingkungan lab virtual untuk menjalankan berbagai perangkat jaringan, termasuk node berbasis QEMU dan Docker. :contentReference[oaicite:0]{index=0}

---

## Available Images

| Image | Version | Kernel | Format | Type |
|---|---|---:|---|---|
| **PNetLab-v8.2-6.8.84** | v8.2 | 6.8.84 | `.ova` | Ready-to-Deploy |
| **PNetLab-v8-netinstall** | v8 | — | `.ova` | Network Installer |

---

# 1. PNetLab v8.2 — Kernel 6.8.84

### `PNetLab-v8.2-6.8.84.ova`

OVA appliance yang dapat langsung di-import ke platform virtualisasi yang mendukung format Open Virtualization Appliance.

### Download

| Mirror | Link |
|---|---|
| **MediaFire** | https://www.mediafire.com/file/uy10drloalz61a5 |
| **Pixeldrain** | https://pixeldrain.com/u/3WTSKNcY |

### File Information

```text
File     : PNetLab-v8.2-6.8.84.ova
CRC-32   : 10c5d11e
SHA-1    : da0c715704c3fbf810ffd265c2c53f01d8c2c3a6
SHA-256  : 855da18ff00318f08eea373f029cba579865f3a93f0bbfe8eb0767296e8f8e19