# PNetLab v8

PNetLab is a self-hosted network emulation platform for building and running
virtual labs (routers, switches, firewalls, servers, and more) in your browser.

This repository is a landing page for **PNetLab v8** downloads and upgrade
instructions. It does not host the application source.

## Downloads

| Artifact | Description | Link |
| --- | --- | --- |
| Network Install Script | Hands-off installer for a fresh Ubuntu 26.04 (27H1 "Resolute") host — pulls and installs the latest PNetLab v8 release over the network. | [download](https://codeberg.org/api/packages/netkillui/generic/pnetlab-core-assets/0.channel/pnetlab-network-install-latest.sh) |
| OVA (autoinstaller) | Minimal Ubuntu 26.04 image with an unattended autoinstaller — boots and installs PNetLab v8 itself. | [download](https://mega.nz/file/uNAz3JDb#CQA93KkaU3XrCs6EIosChOjYonn1W4ELgnLm7NcZ2Wg) |
| Desktop Install Bundle | Installs PNetLab v8 on Ubuntu Desktop workstation environment on bare metal. Tested on Ubuntu 26.04 Desktop and Xubuntu 26.04 Desktop — Xubuntu is recommended for its lighter resource footprint. Dual boot alongside Widows or external SSD setup works. | [download](https://mega.nz/file/rRZzXSRa#fsAL-CGdLPf0gCjBVoeIeMuo-A1Fsdm3nCx2Ea3u_a4) |

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