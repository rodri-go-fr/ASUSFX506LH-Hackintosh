# Hackintosh for **Asus FX506LHB** macOS Sonoma 14.6.1
**Latest OpenCore version 1.0.1**

<!-- START shields -->
<div>
    <!-- downloads --><a href="https://github.com/RobyRew/ASUS-FX506LHB-Hackintosh_OpenCore/releases">
        <img src="https://img.shields.io/github/downloads/RobyRew/ASUS-FX506LHB-Hackintosh_OpenCore/total" alt="downloads"/>
    </a>
    <!-- version --><a href="https://github.com/RobyRew/ASUS-FX506LHB-Hackintosh_OpenCore/releases/latest">
        <img src="https://img.shields.io/github/release/RobyRew/ASUS-FX506LHB-Hackintosh_OpenCore.svg" alt="latest version"/>
    </a>
     <!-- platform --><a href="https://github.com/RobyRew/ASUS-FX506LHB-Hackintosh_OpenCore">
        <img src="https://img.shields.io/badge/platform-macOS-lightgrey.svg" alt="platform"/>
    </a>
</div>
</br>
<!-- END shields -->

![Asus FX506LHB running macOS Ventura](/Docs/Images/Asus-FX506LHB-macOS.png)

# Specifications
Here's the [Amazon Link](https://www.amazon.es/ASUS-TUF-Gaming-F15-FX506LHB/dp/B09TRDT8DC) for this exact model.

Specification | Working
------------- | -------------
Motherboard:  | FX506LHB **HM470** |
CPU  | i5-10300H ✅
RAM: | **Micron** 8ATF1G64HZ-3G2J1 16GB 1600MHz ✅
iGPU: | **Intel** UHD 630 (Mobile) ✅
dGPU: | **nVidia** GeForce GTX 1650 Ti (DISABLED) |
WiFi & BT  | MT7921 ❌, replaced Intel-AX210NGW ✅
RAM  | Mikron 8GB/24GB 3200MHz ✅
Storage  | Kingston NV1 - M2 ✅
Ethernet  | **RealTek** RTL8168/8111 ✅
Audio: | **RealTek** ALC256 ✅
Trackpad: | **ELAN1200** Precision TouchPad (Type HID) ✅
Keyboard: | PS/2 Keyboard (ISO Spain)✅
Battery & Status Battery | ✅


# Working Status
 - ### **Fully Working**
    - Built-In Display
    - Jack 3.5mm, Speakers & Microphone
    - DC-IN & Battery
    - NVMe & HDD
    - Camera
    - Ethernet
    - Keyboard
    - Trackpad

 - ### **Partially Working**
    - [All USB Ports](Not mapped correctly YET)
    - Continuity Features

- ### **Not Working**
    - dGPU *(nVidia GTX 1050Ti)*
    - HDMI Port
    - Sleep
    - Brightness Control

<details open>
    <summary><h3>&nbsp;&nbsp;🔍&nbsp;&nbsp;In-depth Info</h3></summary>

| Name | Solution |
|:--- |:--- |
| Built-In Display  | Works thanks to `SSDT-PNLF.aml` *(Backlight Fix)* and `WhateverGreen.kext` *(iGPU Fixes)*. |
| All USB Ports | Thanks to `USBMap.aml` *(Ports mapped for macOS)* and `SSDT-EC-USBX-LAPTOP.aml`. |
| Jack 3.5mm, Speakers & Microphone | Thanks to `AppleALC.kext` *(Audio Driver)* and layout setted to "1" (Dec) or "01000000" (Hex). |
| DC-IN & Battery| `VirtualSMC.kext` with `SMCBatteryManager.kext` allows management off charging and Battery Info. |
| NVMe & HDD | It used to be something tricky but having SATA on AHCI Mode on *BIOS/UEFI* and latest firmware for the NVMe is enough. |
| Camera | Is connected via Internal USB and it works. |
| Ethernet | Thanks to `RealtekRTL8111.kext` (Ethernet Driver). |
| Keyboard | Thanks to `VoodooPS2.kext` (Driver for PS2 devices). |
| Trackpad | Thanks to `SSDT-XOSI.aml`(Make some Windows Features Avaible for macOS too) and with `VoodooI2C.kext` in combination with `VoodooI2CHID.kext`(Driver for I2C and HID devices like my trackpad). |
| PowerOff, Reboot & Sleep | Working thanks to having correct configs for CPU, iGPU, disabled dGPU, mapped USB Ports and executed these commands after macOS installation: `sudo pmset autopoweroff 0`, `sudo pmset powernap 0`, `sudo pmset standby 0`, `sudo pmset proximitywake 0`, `sudo pmset tcpkeepalive 0`.|
| | |
| WiFi | The WiFi/BT Card needs to be replaced with a **BCM94352Z**  in order to have FULL Native Wirelless Features. |
| Bluetooth | The WiFi/BT Card needs to be replaced with a **BCM94352Z**  in order to have FULL Native Wirelless Features. |
| HDMI Port | HDMI may not work because of nVIDIA OPTIMUS dGPU+iGPU Combo. |
| Continuity Features | Nothing will without compatible WiFi-BT Card |
| | |
| dGPU | dGPU doesn't have any drivers on any macOS OS. |
</details>

---

# Aditional Info

<!-- CREDITS START -->
<details open>
<summary><h3>Credits</h3></summary>

[Apple](https://apple.com) (macOS)

[OpenCore Team](https://github.com/acidanthera/OpenCorePkg) (Bootloader)

[Dortania](https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/coffee-lake.html#starting-point) (Guide)

[@taarkov](https://github.com/taarkov) (Some ACPI ideas)

---

</details>
<!-- CREDITS END -->
If this guide has been useful for you, don't forget to give me a star ⭐️❤️
