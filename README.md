# OpenCore-Satellite-C40-A-hackintosh

[![Brand](https://img.shields.io/badge/Satellite-C40A-yellow?style=flat&logo=toshiba)](https://www.toshiba.com/)
[![macOS](https://img.shields.io/badge/macOS-Catalina_v10.15.7-red?style=flat&logo=apple)](https://www.apple.com/macos/catalina/)
[![OpenCore](https://img.shields.io/badge/OpenCore-v0.9.0-blue?style=flat&logo=okta)](https://github.com/acidanthera/OpenCorePkg)

Running macOS on Toshiba Satellite C40-A Series with OpenCore UEFI
 
![Screen Shot 2023-03-14 at 20 50 06](https://user-images.githubusercontent.com/108976381/225186116-4082acbc-4423-4b14-b889-ddf82fc87876.png)

 
### How to Get it?

- Open Terminal with Command: $ `git clone https://github.com/Nguyen12345t/OpenCore-Satellite-C40-A-hackintosh.git`
- Or [Download](https://github.com/Nguyen12345t/OpenCore-Satellite-C40-A-hackintosh/archive/refs/heads/main.zip) with Specific Folder Only
- Then copy to EFI Partition USB Installer/HDD/SSD
 
--------------------------------------------------------------------------------------------
 
### Specs :

- [x] <b>BIOS</b>: v1.30 (2016/08/24) Insyde H2O Ultility,
- [x] <b>Model Laptop/Notebook</b>: Toshiba Satellite C40-A Series
- [x] <b>Processor</b>: Intel Core i3-3120M (3) @ 2.5 GHz Ivy Bridge
- [x] <b>Graphics</b>: Intel HD Graphics 4000
- [x] <b>RAM</b>: 4 GB 1600 MHz DDR3
- [x] <b>Disk</b>: 12GB SATA SSD Kingston SA400S37120G(GUID Partition Table)
- [x] <b>Audio</b>: Conexant CX20756
- [x] <b>Wifi+BT</b>: Qualcomm Atheros QCA9565/AR9565 Wireless Network Adapter + AR3012 (Azurewave Tech)
- [x] <b>Ethernet</b>: Qualcomm Atheros AR8162/8166/8168 PCI-E Fast Ethernet Controller
- [x] <b>Others</b>: USB3.0 + USB2.0 ports WebCam, Sysnaptics TouchPad PS/2, ports HDMI/VGA, Alcor Micro USB Card Reader, etc.

--------------------------------------------------------------------------------------------

### BIOS Configuration

Bios Config | Setting 
:---:| :---:
Security -> Secure Boot | Disabled
Intel Virtualization    | Enabled OK / Disabled if you have issues
VT-d | Disabled / Enabled OK
USB Configuration -> XHCI Pre-Boot Mode | Enabled (XHC Only) / Smart Auto (XHC + EHC)
SATA Mode | AHCI
Boot -> Launch CSM | Enabled or Disabled for Resolution Boot OC
 
--------------------------------------------------------------------------------------------
 
### What's Working?

- [x] QE/CI Intel HD Graphics 4000 with VRAM 1536 MB (Native)
- [x] Audio Conexant CX20756 with layout-id 3 + Internal Microphone (SSDT-HPET.aml + Lilu.kext + AppleALC.kext)
- [x] Display brightness PNLF and Fn Keys (Add Device PNLF taken from MacBook ACPI dump)
- [x] Qualcomm Atheros AR9565 Wifi (HS80211Family.kext + AirPortAtheros40.kext)
- [x] LAN Ethernet Atheros AR8162/8166/8168 (AtherosE2200Ethernet.kext)
- [x] Bluetooth AR3012 (Ath3kBT.kext + Ath3kBTInjector.kext)
- [x] Sysnaptics TouchPad PS/2 (VoodooPS2Controller.kext)
- [x] Battery Indicator (SMCBatteryManager.kext)
- [x] WebCam OOB but sometimes blank (UTBMap.kext with FakeID Apple WebCam Interfaces)
- [x] USB2.0 Ports + USB3.0 Ports + Power/Speed (Disable XhciPortLimit + UTBMap.kext)
- [x] Native Power Management CPU (Combination from [ssdtPRGen.sh](https://github.com/Piker-Alpha/ssdtPRGen.sh) Pike R. Alpha
- [x] HDMI, Etc.
 
--------------------------------------------------------------------------------------------
 
### Not Working?

- AirDrop, Handoff, Continuity, Because this chipset and module not supported
- Card Reader, broken port on this laptop, so i not use it

--------------------------------------------------------------------------------------------

### Not Tested?
 
 - Sidecar
 - Universal Control
 
--------------------------------------------------------------------------------------------
 
### Notes

1. Don't use my patch [DSDT.aml & SSDT.aml](https://github.com/Nguyen12345t/OpenCore-Satellite-C40-A-hackintosh/tree/main/OC/ACPI) if you have different <b>ACPI Tables / BIOS Version & Model / Freq CPU PM</b>
2. Config OC for Catalina and older, set (MinDate = -1) & (MinVersion = -1) in 'UEFI' -> 'APFS' section

![Screen Shot 2023-03-15 at 09 54 41](https://user-images.githubusercontent.com/108976381/225193292-d7be51be-3918-424e-ad7e-d0ab24b8bd61.png)

3. You need regenerate serial number for your mac, use [OpenCore](https://mackie100projects.altervista.org/download-opencore-configurator/) Configurator
4. And many more [tools](https://github.com/Nguyen12345t/OpenCore-Satellite-C40-A-hackintosh/tree/main/Tools)

--------------------------------------------------------------------------------------------
 
### Special Thanks and Credits to :

- [Apple](https://www.apple.com)
- [Acidanthera](https://github.com/acidanthera)
- [Rehabman](https://github.com/RehabMan)
- [Mieze](https://github.com/Mieze)
- [Pike R. Alpha](https://github.com/Piker-Alpha)
- [InsanelyMac](https://www.insanelymac.com)
- [HSVN](https://www.facebook.com/groups/hackintoshsvn)
- [Mihari Oyama](https://www.facebook.com/unicornhack)
- [Olarila](http://olarila.com)
- [OSXLatitude](https://osxlatitude.com)
- And Other Developers
