# AX3000HV2 Router Complete Firmware Dump

## Overview

This archive contains a comprehensive firmware and system dump from an AX3000HV2 router running OpenWrt 21.02.1. The data was extracted for OpenWrt device development, GPL compliance analysis, and community contribution purposes.

## Archive Contents: `complete_dump_20250817_020052.tar.gz` (104MB)

## Device Information

- **Model**: AX3000HV2 (Hisense/ECONET Technologies)
- **Hardware Platform**: ECONET Technologies xPON ONU
- **True Model**: C30-401
- **Firmware**: OpenWrt 21.02.1 r16325-88151b8303
- **SoC**: Airoha EN7523
- **WiFi Chipset**: MediaTek MT7916
- **MAC Address**: 20:BE:B4:XX:XX:XX
- **Hardware Version**: C30-401
- **Memory**: 256MB RAM
- **Architecture**: ARM

### Device Identification

#### Primary Identity
- **Marketing Name**: AX3000HV2 (Hisense)
- **Hardware Platform**: ECONET Technologies xPON ONU
- **True Model**: C30-401
- **Chip**: Airoha EN7523 SoC + MT7916 WiFi

#### Critical IDs
- **OUI**: 20:BE:B4 (ECONET Technologies)
- **Serial**: XXXXXX
- **Barcode**: XXXXXX
- **Hardware Version**: C30-401
- **Original Firmware**: FT6.11.032hv

## Archive Contents

### Critical Firmware Components

#### MTD Partition Dumps
- **bootloader.bin** (512KB) - U-Boot bootloader binary
- **tclinux.bin** (40MB) - Complete firmware image
- **kernel.bin** (22MB) - Linux kernel 5.4.55 binary
- **rootfs.bin** (37MB) - Root filesystem image
- **rootfs_data.bin** (8MB) - Data partition overlay
- **art.bin** (3.5MB) - WiFi calibration data for MT7916 (CRITICAL)

#### Additional Partitions
- **tclinux_slave.bin** (29MB) - Backup firmware slot
- **kernel_slave.bin** (25MB) - Backup kernel slot
- **rootfs_slave.bin** (26MB) - Backup rootfs slot
- **user_app.bin** (11MB) - User application partition
- **fpt_data.bin** (5MB) - FPT specific data
- **fpt_overlay.bin** (15MB) - FPT overlay partition

### Hardware Information

#### System Details
- **cpuinfo.txt** - ARM processor details and features
- **meminfo.txt** - Memory configuration and usage
- **kernel_version.txt** - Kernel build information
- **dmesg_full.txt** - Complete boot log with hardware detection
- **uboot_env.txt** - U-Boot environment variables

#### Hardware Mapping
- **iomem.txt** - I/O memory map for device tree creation
- **interrupts.txt** - Hardware interrupt assignments
- **mtd_info.txt** - MTD partition layout and sizes

### Network and Wireless Configuration

#### Network Configuration
- **ip_addr.txt** - Network interface configuration
- **bridge_info.txt** - Bridge setup and VLAN configuration
- **arp_table.txt** - ARP cache entries

#### Wireless Configuration
- **iwconfig.txt** - Wireless interface details
- **iwinfo.txt** - MT7916 capabilities and status
- **Wireless/** - MediaTek wireless driver configuration files
  - **RT2860AP.dat** - 2.4GHz radio configuration
  - **RT2860AP_AC.dat** - 5GHz radio configuration
  - **l1profile.dat** - Wireless profile settings

### System Configuration

#### UCI Configuration
- **uci_export.txt** - Complete UCI configuration dump
- **etc_backup.tar.gz** - Full /etc directory backup

#### Process and Module Information
- **ps_busybox.txt** - Running processes snapshot
- **lsmod.txt** - Loaded kernel modules
- **available_modules.txt** - All available kernel modules
- **proc_modules.txt** - Module dependencies and information

### OpenWrt and GPL Compliance

#### Build Information
- **openwrt_release.txt** - OpenWrt version and build details
- **kernel_config.txt** - Complete kernel configuration
- **packages_installed.txt** - List of installed packages

#### Boot and Runtime
- **kernel_cmdline.txt** - Kernel boot parameters
- **mount_info.txt** - Mounted filesystems
- **filesystem_info.txt** - Device nodes and filesystem details

## File Structure

```
complete_dump_20250817_020052/
├── README.md (this file)
├── Firmware_Dumps/
│   ├── bootloader.bin
│   ├── tclinux.bin
│   ├── kernel.bin
│   ├── rootfs.bin
│   ├── rootfs_data.bin
│   ├── art.bin
│   └── [other partition dumps]
├── Hardware_Info/
│   ├── cpuinfo.txt
│   ├── meminfo.txt
│   ├── dmesg_full.txt
│   ├── iomem.txt
│   └── interrupts.txt
├── Network_Config/
│   ├── ip_addr.txt
│   ├── iwconfig.txt
│   ├── iwinfo.txt
│   └── bridge_info.txt
├── System_Config/
│   ├── uci_export.txt
│   ├── etc_backup.tar.gz
│   ├── lsmod.txt
│   └── kernel_config.txt
├── Wireless/
│   ├── RT2860AP.dat
│   ├── RT2860AP_AC.dat
│   └── l1profile.dat
└── GPL_Compliance/
    ├── openwrt_release.txt
    ├── packages_installed.txt
    └── kernel_cmdline.txt
```

## Potential OpenWrt Development Value

This dump may be useful for OpenWrt development efforts. It contains:

### Device Definition Data
- MTD partition layout with sizes and content
- WiFi calibration data (art.bin) - may be important for MT7916
- Bootloader dump for boot sequence analysis
- OpenWrt configuration as reference
- Hardware detection logs showing components

### GPL Compliance Information
- Kernel configuration data
- Loaded modules and dependencies
- Build information and OpenWrt version details
- Package list with versions

### Driver Development Resources
- MT7916 wireless configuration files
- Airoha EN7523 register maps (iomem)
- Device tree information
- Interrupt assignments and hardware layout

## Usage for OpenWrt Development

### Device Definition Creation
1. Use **mtd_info.txt** for partition layout
2. Reference **art.bin** for WiFi calibration preservation
3. Analyze **dmesg_full.txt** for hardware initialization sequence
4. Use **iomem.txt** and **interrupts.txt** for device tree creation

### Driver Development
- **Wireless/** directory contains MT7916 driver configurations
- **kernel_config.txt** shows enabled kernel features
- **lsmod.txt** lists required kernel modules

### Build Configuration
- **kernel_config.txt** provides complete kernel build settings
- **packages_installed.txt** lists required OpenWrt packages
- **openwrt_release.txt** contains build version information

### Device Tree Creation
- Use **iomem.txt** for memory mapping
- Use **interrupts.txt** for IRQ assignments
- Use **dmesg_full.txt** for hardware detection sequence
- Use **kernel_cmdline.txt** for boot parameters

### Files of Potential Interest for OpenWrt Port
1. **art.bin** - May be important for WiFi functionality
2. **bootloader.bin** - For boot sequence understanding
3. **kernel_config.txt** - For build configuration reference
4. **mtd_info.txt** - For partition layout information
5. **Wireless/** - For MT7916 driver configuration reference

## Critical Files for WiFi Functionality

The **art.bin** file contains WiFi calibration data specific to this hardware and may need to be preserved when porting to ensure proper wireless functionality. This file contains:
- RF calibration data for MT7916
- Power amplifier settings
- Antenna configuration
- Regulatory domain information

## Technical Specifications

### Partition Layout (MTD)
```
mtd0: 00080000 "bootloader" (512KB)
mtd1: 02800000 "tclinux" (40MB)
mtd2: 015a0000 "kernel" (22MB)
mtd3: 024b6d68 "rootfs" (37MB)
mtd4: 01d00000 "tclinux_slave" (29MB)
mtd5: 01860000 "kernel_slave" (25MB)
mtd6: 019a8fb0 "rootfs_slave" (26MB)
mtd7: 00b00000 "user_app" (11MB)
mtd8: 00800000 "rootfs_data" (8MB)
mtd9: 00500000 "fpt_data" (5MB)
mtd10: 00f00000 "fpt_overlay" (15MB)
mtd11: 00380000 "art" (3.5MB)
```

### Wireless Capabilities
- **2.4GHz**: HE40 mode (WiFi 6), 2x2 MIMO
- **5GHz**: HE160 mode (WiFi 6), 2x2 MIMO
- **Standards**: 802.11ax/ac/n/g/b/a
- **Security**: WPA3/WPA2/WEP support

## Usage Instructions

### Extract Archive
```bash
tar -xzf complete_dump_20250817_020052.tar.gz
```

## Security and Privacy

Note: This dump may contain sensitive information. Users should review and sanitize as needed:
- May contain WiFi credentials and system passwords
- Review configuration files before sharing
- Consider security implications of shared data
- Hardware and configuration data included as-is

## GPL Compliance

This dump contains information that may be useful for GPL compliance analysis:
- Complete kernel configuration
- Source package versions
- Build system information
- Module dependencies

## Potential Community Impact

This dump may assist with:
- Adding AX3000HV2/C30-401 support to OpenWrt
- Developing Airoha EN7523 SoC support
- Improving MT7916 wireless driver
- Creating device tree definitions
- GPL compliance analysis for derivative works

## Extraction Details

- **Date**: August 17, 2025, 02:00 UTC
- **Source**: AX3000HV2 at 10.1.100.2
- **Method**: SSH extraction using BusyBox utilities
- **Archive Size**: 104MB compressed
- **Total Files**: 50+ individual dumps and configurations

## Community Contribution

This dump is intended for:
- OpenWrt device support development
- Airoha EN7523 SoC support improvement
- MT7916 wireless driver enhancement
- GPL compliance verification
- Community device definition creation

This data dump may be helpful for adding AX3000HV2/C30-401 support to the OpenWrt project.