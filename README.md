# Hackintosh
OpenCore EFI for Lenovo T480s
In that case I use rEFInd + OC because booting to Windows 10 was failing.

## Specification
| **Component** | **Model** |
| ------------- | --------- |
| CPU | Intel Kaby Lake i7-8550u |
| RAM | 16GB (2 x 16GB) Samsung DDR4 @2400MHz |
| IGPU | Intel Graphics UHD 620	|
| NVMe 1 | Samsung SSD 970 EVO Plus 500GB |
| Audio | Realtek ACL257 |
| Wireless | DW1560 Broadcom BCM94352Z |

**rEFInd version**: [0.13.2](https://github.com/dortania/Hackintosh-Mini-Guides/blob/master/refind.md)
**OpenCore version**: [0.7.3](https://github.com/acidanthera/opencorepkg/releases)

## Compatible macOS versions
 - Mojave (10.14.6)

## What Works
 - Wi-Fi : DW1560
 - Bluetooth
 - HDMI
 - Internal/External audio jacks
 - Sleep/Wake up

## What Doesn't Work
 - Fingerprint Reader Synaptics
 - Card Reader Realtek


## How to use
  1. Make your USB installer with [**this guide**](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/)
  	sudo /Applications/Install\ macOS\ YOUR\ VERSION.app/Contents/Resources/createinstallmedia --volume /Volumes/USB --nointeraction
  2. Clone the repository and paste "BOOT" and "OC" directories into your's pendrive "EFI" folder
  3. Download [**GenSMBIOS**](https://github.com/corpnewt/GenSMBIOS) to generate unique SMBIOS information. Run it and follow all steps, as the model select **MacBookPro15,4 1**.
  4. Boot it!  

**You CAN NOT use SMBIOS from this repository, it MUST be unique for every macOS installation**

## Steps
 - BIOS:
 	- Turn off Secure Boot


 		
## Post Installation
- Move your OpenCore EFI folder to a MacOS drive: https://dortania.github.io/OpenCore-Post-Install/universal/oc2hdd.html#grabbing-opencore-off-the-usb

## Hints
- If you've dual boot:
	- To enable macOS-only SMBIOS injection (disabled for Windows 10):
		- Kernel → Quirks → CustomSMBIOSGuid → True
		- Platforminfo → UpdateSMBIOSMode → Custom
	- To have UTC clock and fix Windows 10 issues : DualBoot/UniversalTimeFix.reg
	- Disable Fast Boot on Windows 10 : DualBoot/DisableFastBoot.reg
	- NTFS r/w support : brew install --cask osxfuse; brew install --cask mounty


## Credits
 - [[Kext] Lilu v1.5.3](https://github.com/acidanthera/Lilu)
 - [[Kext] WhateverGreen v1.4.9](https://github.com/acidanthera/WhateverGreen)
 - [[Kext] VirtualSMC/SMCBatteryManager/SMCProcessor/SMCSuperIO v1.2.7](https://github.com/acidanthera/VirtualSMC)
 - [[Kext] AppleALC v1.6.1](https://github.com/acidanthera/AppleALC)
 - [[Kext] NVMeFix v1.0.9](https://github.com/acidanthera/NVMeFix)
 - [[Kext] NoTouchID v1.0.4](https://github.com/al3xtjames/NoTouchID)
 - [[Kext] VoodooPS2Controller v2.2.5](https://github.com/acidanthera/VoodooPS2)
 - [[Kext] VoodooSMBUS v3.0](https://github.com/VoodooSMBus/VoodooSMBus)
 - [[Kext] CPUFriend v1.2.4](https://github.com/acidanthera/CPUFriend)
 - [[Kext] AppleBacklightSmoother v1.0.2](https://github.com/hieplpvip/AppleBacklightSmoother)
 - [[Kext] AirportBrcmFixup v2.1.3](https://github.com/acidanthera/AirportBrcmFixup)
 - [[Kext] BrcmPatchRAM v2.6.0](https://github.com/acidanthera/BrcmPatchRAM)



# Hackitosh Apps
- Install Homebrew : 
	- /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
- Karabiner :
	- brew install --cask karabiner-elements
	- Import settings from karabiner/ folder
	- If doesn't work change keyboard to "virtual" and change to USB Keyboard again
- Hackintool
- OpenCore Configurator


# MacOS Apps
- iTerm2 + Oh My Zsh! :
	- brew install --cask iterm2
	- brew install zsh zsh-completions
	- Follow https://www.freecodecamp.org/news/how-to-configure-your-macos-terminal-with-zsh-like-a-pro-c0ab3f3c1156/
- XtraFinder : https://www.trankynam.com/xtrafinder/
- HyperDock : brew install --cask hyperdock
- HyperSwitch : brew install --cask hyperswitch
- CopyQ : brew install --cask copyq
- Caffeine : brew install --cask caffeine
- iStat Menus : brew install --cask istat-menus
- Keka : brew install --cask keka
- Lightshot Screenshot : https://app.prntscr.com/es/download.html
- MonitorControl : brew install --cask monitorcontrol
- Numi : brew install --cask numi
- PingMenu : brew install --cask pingmenu
- Tunnelblick : brew install --cask tunnelblick
- Sublime Text : brew install --cask sublime-text
