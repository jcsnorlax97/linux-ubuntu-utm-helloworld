# HelloWorld (UTM + Linux & Ubuntu)

## 0. Table of Contents
- [HelloWorld (UTM + Linux & Ubuntu)](#helloworld-utm--linux--ubuntu)
  - [0. Table of Contents](#0-table-of-contents)
  - [1. How to Setup?](#1-how-to-setup)
  - [2. References](#2-references)

## 1. How to Setup?

1. Install **UTM** via **Homebrew** & Open it

2. Create a New Virtual Machine (VM)
   1. Click **"Create a New Virtual Machine"**
   2. Update **"Information"** section
      1. Set **"Name"** to be **"Ubuntu"**
      2. Set **"Style"** to be **"Operating System"**
   3. Update **"System"** section
      1. Set **"Hardware Architecture"** to be **"ARM64 (aarch64)"** (for M1 Macbook)
      2. Set **"Hardware System"** to be **"QEMU 6.1 ARM Virtual Machine (alias of virt-6.1) (virt)"**
      3. Set **"Hardware Memory"** to be **"4096 MB"**
   4. Update **"Drives"** section
      1. Create a **NVMe-Interface** drive.
         1. Click **"New Drive"**
         2. Set **"Interface"** to be **"NVMe"**
         3. Set **"Size"** to be **"20 GB"**
         4. Click **"Create"**
      2. Create a **removable USB-Interface** drive.
         1. Click **"New Drive"**
         2. Check the **"Removable"** checkbox
         3. Set **"Interface"** to be **"USB"**
         4. Click **"Create"**
   5. Click **"Save"**
3. Download **"Ubuntu Server for ARM"** from Ubuntu's official site.
   1. Go to [Ubuntu - Downloads - Ubuntu Server for ARM](https://ubuntu.com/download/server/arm)
   2. Click **"Download Ubuntu 20.04.3 LTS"**
4. Import the ISO image of **"Ubuntu Server for ARM"** into the VM via **CD/DVD** slot
   1. Click the **CD/DVD slot**
   2. Click **"Browse"**
   3. Select the ISO image, e.g. `ubuntu-20.04.3-live-server-arm64.iso`
   4. Click **"Open"**
5. Install Ubuntu Server in the VM
   1. Run the VM
   2. Select "Install Ubuntu Server"
   3. Select "English" to be the language
   4. Select "English (US)" to be the keyboard layout and variant
   5. Keep the default configuration for "Proxy", "Ubuntu Archive Mirror", "Storage"
   6. Select "Continue" to "Confirm destructive action"
   7. Fill in your profile (server name, username & password)
   8. Select "Install OpenSSH server" in "SSH Setup" section
   9. Keep the default configuration for "Featured Server Snaps"
   10. Select **"Reboot Now"** after the installation
       1.  Note: If failed, simply close & re-run the VM
6. **Restart** the VM
   1.  Click **"Drive Image Options"** on the menu bar & Eject **"CD/DVD (ISO) Image usb: ubuntu-20.04.3-live-server-arm64.iso"**
   2.  Click **"Restarts the VM"** on the menu bar & Click **"OK"**
7. Install **"Ubuntu Desktop"**
   1. Login Ubuntu using the username & password
   2. `sudo apt update`
   3. `sudo apt install tasksel`
   4. `sudo tasksel install ubuntu-desktop`
      - Note: If failed, re-execute this same command once again
   5. `sudo reboot`
      - Note: If failed, simply close & re-run the VM
8. Install **"Spice Guest Agent Tools"**
   1. Open "Terminal"
   2. `sudo apt install spice-vdagent spice-webdavd`
   3. Close "Terminal"
   4. Turn the VM's power off ("Power Off...")
9. Edit VM after Spice Guest Agent Tools are installed
   1. Edit the Ubuntu VM
   2. Check the following checkboxes in the **Sharing** section
      1. "Shared Directory" -> **"Enable Directory Sharing"** checkbox
   3. Check the following checkboxes in the **"Display"** section
      1. "Resolution" -> "Fit To Screen" checkbox
      2. "Resolution" -> "Retina Mode" checkbox
   4. Click "Save"
10. Run Ubuntu!
    1.  Run the Ubuntu VM
    2.  Open "Terminal"
    3.  `sudo apt install neofetch`
    4.  `neofetch`

## 2. References

- [Ubuntu Install on M1 MacBook Air - Virtualization and Benchmarking!](https://www.youtube.com/watch?v=hnwK-nkXolc)
- [Homebrew - utm](https://formulae.brew.sh/cask/utm#default)
- [UTM](https://mac.getutm.app/)