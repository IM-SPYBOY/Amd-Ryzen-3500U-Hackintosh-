AMD Ryzen 3500U Hackintosh

OpenCore EFI for AMD Ryzen 3500U Hackintosh systems.

What is Working

* iGPU
* Touchpad
* Keyboard
* Ethernet
* Audio
* Apple ID
* HDMI
* USB Ports
* Wi-Fi
* Bluetooth
* Camera
* AirPlay
* Screen Mirroring
* Handoff
* Sleep & Wake
* Battery Status
* Backlight & Brightness

Installation Steps

1. Download your desired macOS version by following the OpenCore Install Guide.
    Note: Screen Mirroring works only on macOS Monterey and earlier.
2. Download the EFI folder attached to this repository.
3. Use SSDTTime to dump your DSDT.aml file and copy it to:

EFI/OC/ACPI

    Replace the existing DSDT.aml file.
4. Copy the com.apple.recovery.boot folder along with the EFI folder to a FAT32 formatted USB drive or partition.
5. Boot your system and select the created USB drive or partition from the boot menu.
6. Once macOS Recovery has booted:
    * Connect to Wi-Fi.
    * Open Disk Utility.
    * Select the target partition.
    * Format it as APFS.
7. Return to macOS Recovery and select Reinstall macOS. Continue with the installation process.
8. The system may reboot multiple times during installation. Select macOS Installer from the OpenCore boot menu whenever required.
    Note: If the system hangs during boot, force restart it by holding the power button.

Fixing Sleep/Wake Properly

1. Edit your DSDT and modify the _PWR values by following the Sleep/Wake Fix Guide.
2. For reliable Sleep/Wake functionality, navigate to:

/Library/Preferences/

    Delete files containing com.apple.PowerManagement in their name using Terminal.
    These files will automatically regenerate after rebooting the system.
3. If the system reboots after long periods of sleep, try disabling Standby using Hackintool.
