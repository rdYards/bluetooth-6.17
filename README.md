Here’s an updated `README.md` with setup instructions for Ubuntu, Debian, Fedora, and Arch Linux:

---

# Bluetooth 6.17 DKMS Driver

This repository provides a DKMS module with patches for unsupported hardware such as the following below for Linux kernel version 6.17.
- ID 0489:e112 Foxconn / Hon Hai Bluetooth Radio

## Installation

### Prerequisites
- Git
- DKMS
- Kernel headers (usually installed automatically with DKMS)

---

## Setup Instructions

### Ubuntu/Debian
```bash
sudo apt update
sudo apt install git dkms
```

### Fedora
```bash
sudo dnf install git dkms kernel-devel kernel-headers
```

### Arch Linux
```bash
sudo pacman -S git dkms linux-headers
```

---

### Install patched Bluetooth Driver
```bash
git clone https://github.com/rdYards/bluetooth-6.17.git
sudo dkms add ./bluetooth-6.17
sudo dkms install btusb/6.17
```
---

**Note:** After installation, you may need to reboot or reload the `btusb` module:
```bash
sudo modprobe -r btusb
sudo modprobe btusb
```
---
#### Support for other hardware
If you have hardware you would like supported please open an issue.
---
Thank you to https://github.com/jeremyb31/bluetooth-6.8 for teaching me how to patch.
