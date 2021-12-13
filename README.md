## Disclaimer
The guide is only for educational Purpose.
I am not responsile for any damage caused to your device.
Make sure you read this guide as well as other guides that has been linked to the page before continuing.
## Specifications
```
Machine:   Type: Laptop System: LENOVO product: 81DE v: Lenovo ideapad 330-15IKB serial: <filter> 
           Chassis: type: 10 v: Lenovo ideapad 330-15IKB serial: <filter> 
           Mobo: LENOVO model: LNVNB161216 v: NO DPK serial: <filter> UEFI: LENOVO v: 8TCN61WW 
           date: 05/19/2021 
Battery:   ID-1: BAT0 charge: 16.7 Wh condition: 27.8/35.0 Wh (79%) volts: 7.9/7.5 
           model: SMP L16M2PB2 serial: <filter> status: Unknown 
CPU:       Topology: Quad Core model: Intel Core i5-8250U bits: 64 type: MT MCP arch: Kaby Lake 
           rev: A L2 cache: 6144 KiB 
           flags: avx avx2 lm nx pae sse sse2 sse3 sse4_1 sse4_2 ssse3 vmx bogomips: 28800 
           Speed: 3337 MHz min/max: 400/3400 MHz Core speeds (MHz): 1: 3400 2: 3400 3: 3400 
           4: 3400 5: 3400 6: 3400 7: 3400 8: 3400 
Graphics:  Device-1: Intel UHD Graphics 620 vendor: Lenovo driver: i915 v: kernel bus ID: 00:02.0 
           chip ID: 8086:5917 
           Device-2: NVIDIA GP108M [GeForce MX150] vendor: Lenovo driver: nvidia v: 470.86 
           bus ID: 01:00.0 chip ID: 10de:1d10 
           resolution: 1366x768~60Hz 
           OpenGL: renderer: NVIDIA GeForce MX150/PCIe/SSE2 v: 4.6.0 NVIDIA 470.86 
           direct render: Yes 
Audio:     Device-1: Intel Sunrise Point-LP HD Audio vendor: Lenovo driver: snd_hda_intel 
           v: kernel bus ID: 00:1f.3 chip ID: 8086:9d71 
Network:   Device-1: Realtek RTL8111/8168/8411 PCI Express Gigabit Ethernet vendor: Lenovo 
           Device-2: Intel Dual Band Wireless-AC 3165 Plus Bluetooth driver: iwlwifi v: kernel 
           port: 3000 bus ID: 03:00.0 chip ID: 8086:3166 
           IF: wlp3s0 state: up mac: <filter> 
           IF-ID-1: virbr0 state: down mac: <filter> 
           IF-ID-2: virbr0-nic state: down mac: <filter> 
Drives:    Local Storage: total: 1.13 TiB 
           Seagate model: ST1000LM035-1RK172 size: 931.51 GiB 
           speed: 6.0 Gb/s
```
---
## Used

### Guides:

-   [Dortania OpenCore guide](https://dortania.github.io/OpenCore-Install-Guide/) for Vanilla macOS/ Hackintosh setup
-   [RehabMan DSDT patching](https://www.tonymacx86.com/threads/guide-how-to-patch-dsdt-for-working-battery-status.116102/) for working battery status
-   [WEG Framebuffer patching](https://github.com/acidanthera/WhateverGreen/blob/master/Manual/FAQ.IntelHD.en.md)

### Tools:

-   [SSDTTime](https://github.com/corpnewt/SSDTTime)
-   [USBMap](https://github.com/corpnewt/USBMap)
-   [Hackintool](https://github.com/headkaze/Hackintool)
-   [ProperTree](https://github.com/corpnewt/ProperTree)
-   [gibMacOS](https://github.com/corpnewt/gibMacOS)
## What Works
Everything Works
**Exception**
1. Function keys requires workaroud
2. Nvidia Graphics card is disabled
3. DRM is not supported 

## Procedure
1. The EFI provided Strictly works on Mac OS 12 (*requires little tweaking for previous version*)
2. Set up the Platforminfo/Generic/ section, this is unique to every Hackintosh as it contains SerialNumber, MLB, ROM. Use [this guide](https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/kaby-lake.html#platforminfo)
3. For this setup the SMBIOS of the [MacBookPro15,2 with i5-8259U](https://everymac.com/systems/apple/macbook_pro/specs/macbook-pro-core-i5-2.3-13-mid-2018-true-tone-display-touch-bar-specs.html) is used, as it´s the closest we can match the i5-8250U of the Ideapad.
4. Update major kext like Lilu, Whatevergreen, Airportitlwm bluetoolfixup Intel bluetoothFirmware Virtual SMC AppleALC[follow this](https://dortania.github.io/OpenCore-Install-Guide/ktext.html#kexts)
5. Follow this guide to create the bootlable [guide](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/)
6. For dual boot 
	1. create a NTFS partation and lable it with some name *example MACOS*
	2. boot from USB select disk utility and format the drive in APFS format
	3. Now install mac OS in that drive
7. To fix Function keys use [karabiner elements](https://karabiner-elements.pqrs.org/)
---
## Inspiration
This guide is inspired by 
1. https://github.com/kasti0/Hackintosh_Lenovo-IdeaPad-330s-15ikb
2. https://github.com/LucasDondo/Hackintosh-Lenovo-IdeaPad-330-15IKB-81DE
