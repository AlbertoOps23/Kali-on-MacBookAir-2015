# 🧰 Installation Steps — Kali Linux on MacBook Air 2015
 
This document details the full installation process I followed to reinstall Kali Linux on my **MacBook Air 2015 (Intel i5)** after a macOS update removed my previous dual-boot setup.

---

## 🪜 Step 1 — Background

Originally, I had **macOS + Kali Linux** dual booted successfully.  
After updating macOS (from Big Sur → Monterey), the Kali partition was deleted or overwritten.  
Disk Utility showed 125GB of “free space,” which used to be my Kali partition.

Goal: Reinstall Kali Linux and restore dual boot with working Wi-Fi and tools.

---

## 💾 Step 2 — Creating the Bootable USB

On my Windows PC:

1. Downloaded the official **Kali Linux ISO** from [kali.org](https://www.kali.org/get-kali/).  
2. Used **Rufus** to create a bootable USB drive:
   - Partition scheme: **GPT**
   - Target system: **UEFI (non-CSM)**
   - File system: **FAT32**
   - Wrote the ISO to a 16GB USB drive.

---

## ⚙️ Step 3 — Preparing the MacBook

1. Booted into macOS and opened **Disk Utility**.  
2. Shrunk the macOS partition to make **125GB of free space** for Kali.  
3. Inserted the USB installer.  
4. Rebooted and held the **Option (⌥)** key at startup.  
5. Selected the **Kali Linux USB** to boot.

---

## 🧩 Step 4 — Installing Kali (No Internet)

1. Selected **Graphical Install** from the boot menu.  
2. Followed normal setup:
   - Language, location, keyboard layout.  
   - Set hostname and user info.  
3. At **network setup**, no network adapters were detected (Broadcom driver issue).  
4. Tried using iPhone USB hotspot — not detected.  
5. Continued **without a network connection**.

During installation:
- Selected **XFCE** as desktop environment.  
- Chose **“All Tools”** (this triggered a 2600+ package download attempt).

Despite no internet, installation proceeded and finished successfully with **no major errors**.

---

## 🔁 Step 5 — First Boot

1. Removed the USB installer.  
2. Rebooted into Kali.  
3. System loaded successfully into XFCE desktop.  
4. Still, **no Wi-Fi networks detected** (as expected).

---

## 🔍 Step 6 — Identifying the Network Adapter And Troubleshooting

Opened a terminal and ran:

```bash
lspci | grep Network
Broadcom Inc. and subsidiaries BCM4360 802.11ac Wireless Network Adapter
```
🧰 Final Setup and Dual Boot Verification

Performed a full system update.
Installed any missing packages or tools.

Rebooted and verified dual-boot access using the Option (⌥) key — both macOS and Kali Linux booted normally.

Wi-Fi connection persisted after reboot.
