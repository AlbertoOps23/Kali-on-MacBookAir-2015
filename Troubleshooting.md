# 🧩 Troubleshooting — Kali Linux on MacBook Air 2015
 
This file documents the real issues I encountered while reinstalling Kali Linux on my **MacBook Air (2015, Intel i5)** after macOS updates erased my previous dual boot.  
These are the exact fixes that worked for me.

---

## ⚠️ No Network Connection During Installation

**Problem:**  
During the Kali installation, no Wi-Fi networks appeared, and the system didn’t detect any network hardware.  
Even connecting my iPhone via USB hotspot didn’t provide internet access.

**What I Did:**
- Continued the installation **without setting up the network**.
- Selected **XFCE with all tools** during package selection.
- The installation completed successfully without errors, even with no internet connection.

---

## 🧰 After First Boot — Fixing Wi-Fi

After removing the USB installer and booting into Kali for the first time:
- Logged into the desktop successfully.
- Plugged in my **iPhone via USB** and enabled **Personal Hotspot**.
- This time, the hotspot was detected and worked as an internet source.

---

## 🧩 Identifying the Network Adapter

I checked my Wi-Fi hardware by running:
```bash
lspci | grep Network
```
Output showed:
```bash
Broadcom Inc. and subsidiaries BCM4360 802.11ac Wireless Network Adapter
```
⚙️ Installing the Correct Driver

At first, I tried:
```bash
sudo apt install broadcom-sta-dkms
sudo modprobe wl
```
But received:
```bash
modprobe: FATAL: Module wl not found in directory /lib/modules/...
```
To fix this, I installed the latest kernel image and headers, then rebooted:
```bash
sudo apt install linux-image-amd64 linux-headers-amd64
sudo reboot
```
After the reboot, Wi-Fi networks appeared instantly and connected normally. ✅
