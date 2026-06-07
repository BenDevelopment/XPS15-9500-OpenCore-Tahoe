# Dell XPS 15 9500 OpenCore Tahoe

Premium OpenCore configuration for the Dell XPS 15 9500, built as a clean, stable, and maintainable macOS Tahoe EFI archive.

This repository contains a complete EFI folder that can be used as a working baseline for an XPS 15 9500 running OpenCore. It includes ACPI patches, drivers, kexts, boot resources, tools, and the main OpenCore configuration.

## Overview

- Target machine: Dell XPS 15 9500
- Bootloader: OpenCore
- Target macOS: Tahoe
- Configured SMBIOS: `MacBookPro16,4`
- Main folder: `EFI/OC`
- Main configuration: `EFI/OC/config.plist`

## Repository Layout

```text
EFI/
├── BOOT/
│   └── BOOTx64.efi
└── OC/
    ├── ACPI/
    ├── Drivers/
    ├── Kexts/
    ├── Resources/
    ├── Tools/
    ├── OpenCore.efi
    ├── config.plist
    └── oldConfig.plist
```

## Highlights

- Full kext set for audio, battery, trackpad, Bluetooth, Wi-Fi, NVMe, SMC sensors, and core system support.
- OpenCanopy resources included for a polished boot picker experience.
- ACPI files tailored for the Dell XPS 15 9500.
- Clean Git archive without EFI partition system folders.

## Before You Use It

This EFI is machine-specific. Before using it on another XPS 15 9500, carefully review the following:

- `PlatformInfo`: generate your own SMBIOS values with GenSMBIOS or an equivalent tool.
- `config.plist`: validate ACPI, kext, and driver entries with ProperTree or OpenCore Configurator.
- Wi-Fi/Bluetooth: adjust kexts according to your wireless card.
- NVRAM: reset NVRAM after major configuration changes.
- Backup: always keep a bootable USB rescue EFI.

## Quick Installation

1. Mount the target disk's EFI partition.
2. Copy the `EFI` folder to the root of that partition.
3. Review `EFI/OC/config.plist`.
4. Reboot and select OpenCore.
5. Once boot is confirmed, keep a backup copy of this EFI.

## Maintenance

For clean updates:

1. Back up the working EFI.
2. Update OpenCore with the matching release binaries.
3. Update kexts one at a time.
4. Refresh the ProperTree snapshot if needed.
5. Test from a USB drive before replacing the main EFI.

## Disclaimer

This configuration is provided as a personal archive and technical baseline. Incorrect SMBIOS values, incompatible kexts, or invalid NVRAM settings can prevent the system from booting. Always test before deploying to your primary EFI partition.

## Credit

Maintained by [BenDevelopment](https://github.com/BenDevelopment).
