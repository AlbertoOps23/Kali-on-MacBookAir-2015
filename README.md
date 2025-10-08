# Kali-Linux-on-MacBookAir-2015

Documenting the process of reinstalling Kali Linux on a 2015 MacBook Air after macOS update erased the dual boot. Includes driver fixes for Broadcom BCM4360 Wi-Fi and offline installation troubleshooting.

## 💻 Overview
This project documents how I reinstalled Kali Linux on my 2015 MacBook Air (Intel i5) after macOS updates removed my previous dual boot.  
It covers:
- Creating a Kali Linux USB installer on Windows (Rufus)
- Partitioning the Mac drive for dual boot
- Installing Kali without network connectivity
- Fixing Wi-Fi (Broadcom BCM4360) after installation
- Final verification and setup

## 🧰 System Info
- **Device:** MacBook Air (Early 2015, Intel i5)
- **Wi-Fi Chip:** Broadcom BCM4360 802.11ac
- **Operating Systems:** macOS Monterey + Kali Linux
- **Boot Mode:** Dual Boot (Option key on startup)

## ⚙️ Key Fix
After installation, Kali didn’t detect any networks.  
Fix applied:
```bash
sudo apt install linux-image-amd64 linux-headers-amd64
sudo reboot 
