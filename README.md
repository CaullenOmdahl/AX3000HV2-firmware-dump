# AX3000HV2 Router Complete Firmware Dump

## Overview

This archive contains a comprehensive firmware and system dump from an AX3000HV2 router running OpenWrt 21.02.1. The data was extracted for OpenWrt device development, GPL compliance analysis, and community contribution purposes.

## Archive Contents: `comprehensive_dump_20250817_031148.tar.gz` (23MB)

## 🚀 NEW: OpenWrt Porting Data Collection

**Added August 17, 2025** - Comprehensive data collection for OpenWrt device porting analysis.

### OpenWrt Porting Assessment: **HIGH VIABILITY** ✅

Based on extensive research and hardware analysis, this device shows excellent potential for OpenWrt porting:

- ✅ **SoC Support**: Airoha EN7523 has existing OpenWrt support (airoha/generic target)
- ✅ **Wireless Support**: MediaTek MT7916 supported via mt76 driver family  
- ✅ **Memory Requirements**: 473MB RAM exceeds OpenWrt 2025 requirements
- ✅ **Architecture**: ARMv7 Cortex-A53 well-supported in OpenWrt

### OpenWrt Porting Data Package: `openwrt_porting_data/`

Critical data collected for OpenWrt development:

- **`OPENWRT_PORTING_ANALYSIS.md`** - Comprehensive porting analysis and recommendations
- **`device_tree_raw.txt`** - Complete device tree information from /proc/device-tree
- **`uboot_environment.txt`** - U-Boot environment and kernel boot parameters
- **`gpio_pinmux_info.txt`** - GPIO pin assignments and LED configurations
- **`switch_ethernet_config.txt`** - Ethernet switch and network interface mappings
- **`additional_hardware_info.txt`** - I/O memory maps and hardware detection logs

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
- **bootloader.bin** (512KB) - U-Boot bootloader binary dump
- **kernel.bin** (22MB) - Linux kernel 5.4.55 binary dump  
- **art.bin** (3.5MB) - WiFi calibration data for MT7916 (CRITICAL for wireless functionality)

### Hardware and System Information

#### System Details
- **cpuinfo.txt** - ARM processor details and features
- **system_info.txt** - Complete system information including memory, uptime, and hardware details
- **kernel_details.txt** - Kernel command line, memory mapping, and interrupt assignments
- **kernel_modules.txt** - Loaded kernel modules and dependencies
- **mtd_info.txt** - MTD partition layout and sizes
- **bootloader_hex_sample.txt** - Hexdump sample of bootloader for analysis

### Network and Wireless Configuration

#### Network Configuration  
- **network_info.txt** - Complete network interface configuration and routing tables

#### Wireless Configuration
- **uci_config_full.txt** - Complete UCI configuration including wireless settings
- **wireless_config.tar.gz** - Complete wireless driver configuration archive containing:
  - **etc/Wireless/RT2860AP/RT2860AP.dat** - 2.4GHz radio configuration
  - **etc/Wireless/RT2860AP/DBDC_card0.dat** - Dual-band configuration
  - **etc/Wireless/RT2860AP_AC/RT2860AP.dat** - 5GHz radio configuration  
  - **etc/Wireless/RT2860AP_AC/RT30xxEEPROM.bin** - Wireless EEPROM data
  - **etc/Wireless/l1profile.dat** - Wireless profile settings

## File Structure

### Main Archive: `comprehensive_dump_20250817_031148.tar.gz` (23MB)

```
comprehensive_dump_20250817_031148.tar.gz (23MB)
└── comprehensive_dump/
    ├── art.bin (3.5MB) - WiFi calibration data for MT7916
    ├── bootloader.bin (512KB) - U-Boot bootloader binary
    ├── bootloader_hex_sample.txt - Hexdump sample of bootloader
    ├── cpuinfo.txt - ARM processor details and features
    ├── kernel.bin (22MB) - Linux kernel binary
    ├── kernel_details.txt - Kernel command line, memory mapping, interrupts
    ├── kernel_modules.txt - Loaded kernel modules and dependencies
    ├── mtd_info.txt - MTD partition layout and sizes
    ├── network_info.txt - Network interface configuration and routing
    ├── system_info.txt - System information, memory, uptime, hardware
    ├── uci_config_full.txt - Complete UCI configuration
    └── wireless_config.tar.gz - Complete wireless driver configuration
        └── etc/Wireless/
            ├── RT2860AP/
            │   ├── RT2860AP.dat - 2.4GHz radio configuration
            │   └── DBDC_card0.dat - Dual-band configuration
            ├── RT2860AP_AC/
            │   ├── RT2860AP.dat - 5GHz radio configuration
            │   └── RT30xxEEPROM.bin - Wireless EEPROM data
            └── l1profile.dat - Wireless profile settings
```

### OpenWrt Porting Data: `openwrt_porting_data/`

```
openwrt_porting_data/
├── OPENWRT_PORTING_ANALYSIS.md - Comprehensive porting analysis and recommendations
├── additional_hardware_info.txt - I/O memory maps and hardware detection logs
├── device_tree_detailed.txt - Detailed device tree information
├── device_tree_properties.txt - Device tree properties
├── device_tree_raw.txt - Raw device tree data from /proc/device-tree
├── gpio_pinmux_info.txt - GPIO pin assignments and LED configurations
├── switch_ethernet_config.txt - Ethernet switch and network interface mappings
└── uboot_environment.txt - U-Boot environment and kernel boot parameters
```

### Additional Data Collections

```
AX3000HV2_OpenWrt_DevFiles/ - Original firmware development files
├── DEVICE_SUMMARY.md - Device summary and specifications
├── config_*.txt - UCI configuration exports
├── cpuinfo.txt, dmesg_boot.txt, kernel_*.txt - System information
├── filesystem_info.txt, storage_partitions.txt - Storage details
└── etc/Wireless/ - Wireless driver configuration files

device_tree_complete.dts - Complete device tree source (extracted)
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
3. Analyze **kernel_details.txt** for hardware initialization, memory mapping, and interrupts
4. Use **system_info.txt** for hardware detection sequence

### Driver Development
- **wireless_config.tar.gz** contains complete MT7916 driver configurations
- **kernel_modules.txt** shows loaded modules and dependencies
- **kernel.bin** provides complete kernel binary for analysis

### Build Configuration
- **uci_config_full.txt** provides complete system configuration
- **kernel_modules.txt** lists required kernel modules and dependencies
- **system_info.txt** contains kernel version and build information

### Device Tree Creation
- Use **kernel_details.txt** for memory mapping and IRQ assignments
- Use **system_info.txt** for hardware detection sequence
- Use **bootloader_hex_sample.txt** for boot sequence analysis

### Files of Potential Interest for OpenWrt Port
1. **art.bin** - Critical for WiFi functionality (MT7916 calibration data)
2. **bootloader.bin** - For boot sequence understanding and U-Boot analysis
3. **kernel.bin** - Complete kernel binary for reverse engineering
4. **mtd_info.txt** - For partition layout information
5. **wireless_config.tar.gz** - For MT7916 driver configuration reference
6. **kernel_modules.txt** - For understanding driver dependencies
7. **system_info.txt** - For hardware detection and memory mapping

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
tar -xzf comprehensive_dump_20250817_031148.tar.gz
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

- **Date**: August 17, 2025, 03:11 UTC
- **Source**: AX3000HV2 at 10.1.100.2 via SSH
- **Method**: Direct MTD partition dumping and system information collection
- **Archive Size**: 23MB compressed
- **Total Files**: 12 files including critical MTD partitions and system configuration
- **Key Components**: 3 MTD partition binaries, 8 system information files, 1 wireless configuration archive

## Community Contribution

This dump is intended for:
- OpenWrt device support development
- Airoha EN7523 SoC support improvement
- MT7916 wireless driver enhancement
- GPL compliance verification
- Community device definition creation

This data dump may be helpful for adding AX3000HV2/C30-401 support to the OpenWrt project.