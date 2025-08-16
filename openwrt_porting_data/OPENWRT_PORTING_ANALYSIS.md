# OpenWrt Porting Analysis for AX3000HV2 (C30-401)

## Executive Summary

This document provides a comprehensive analysis of the AX3000HV2 router's hardware and firmware data for OpenWrt porting purposes. Based on extensive research and data collection, the device shows **HIGH viability** for OpenWrt porting with existing platform support for the Airoha EN7523 SoC.

## Device Specifications

### Hardware Platform
- **SoC**: Airoha EN7523 (ARMv7 Cortex-A53 dual-core)
- **Architecture**: ARM cortex-a7 (OpenWrt target: airoha/generic)
- **Memory**: 473MB RAM (exceeds 256MB OpenWrt requirement)
- **Wireless**: MediaTek MT7916 (WiFi 6, 2.4/5GHz dual-band)
- **Ethernet**: Integrated switch with multiple ports
- **Flash**: Multiple MTD partitions with 512KB bootloader

### OpenWrt Support Status
- ✅ **SoC Support**: Airoha EN7523 has basic OpenWrt support in airoha/generic target
- ✅ **Wireless Support**: MT7916 supported via mt76 driver family (kernel 5.9+)
- ✅ **Memory Requirements**: Meets modern OpenWrt requirements for 2025
- ⚠️ **Device Tree**: Requires custom device tree development

## Data Collection Results

### ✅ Successfully Collected
1. **Device Tree Information** (`device_tree_raw.txt`)
   - Complete /proc/device-tree filesystem dump
   - Hardware component mappings
   - Memory and interrupt assignments

2. **U-Boot Environment** (`uboot_environment.txt`)
   - Kernel command line parameters
   - Boot configuration details

3. **GPIO and Pinmux Data** (`gpio_pinmux_info.txt`)
   - LED configuration and triggers
   - GPIO pin assignments
   - Hardware control interfaces

4. **Ethernet Switch Configuration** (`switch_ethernet_config.txt`)
   - Network interface mappings
   - Bridge configurations
   - Physical port information

5. **Additional Hardware Information** (`additional_hardware_info.txt`)
   - I/O memory mappings
   - PCI device enumeration
   - Hardware detection logs

## OpenWrt Porting Assessment

### Strengths for Porting
- **Existing SoC Support**: Airoha EN7523 already has OpenWrt framework
- **Wireless Driver**: MT7916 supported in mt76 driver
- **Hardware Documentation**: Comprehensive data collected
- **Memory Adequate**: 473MB exceeds minimum requirements
- **Standard Architecture**: ARMv7 well-supported in OpenWrt

### Challenges to Address
- **Custom Device Tree**: Will need EN7523-specific device tree development
- **Switch Configuration**: Ethernet switch setup requires proper configuration
- **GPIO Mapping**: LED and button functionality needs proper pin assignment
- **Boot Process**: U-Boot integration and image format requirements

## Critical Files for OpenWrt Development

### High Priority
1. **art.bin** (from comprehensive_dump) - WiFi calibration data (CRITICAL)
2. **bootloader.bin** - U-Boot analysis and boot process understanding
3. **device_tree_raw.txt** - Hardware layout and component mapping
4. **mtd_info.txt** - Partition layout for image creation

### Medium Priority
5. **kernel.bin** - Kernel binary analysis and reverse engineering
6. **gpio_pinmux_info.txt** - LED/button functionality
7. **switch_ethernet_config.txt** - Network port configuration
8. **kernel_modules.txt** - Driver dependencies

## Recommended Next Steps

### 1. Device Tree Development
- Create custom .dts file based on device_tree_raw.txt data
- Define GPIO pin functions for LEDs and buttons
- Configure ethernet switch port mappings
- Set proper memory and interrupt mappings

### 2. Build Configuration
- Set up OpenWrt build environment for airoha/generic target
- Create device-specific image configuration
- Configure kernel modules for MT7916 wireless

### 3. Testing Strategy
- Start with basic boot and console access
- Progressive hardware enablement (ethernet, wireless, GPIO)
- Validation of all hardware functions

## File Manifest

```
openwrt_porting_data/
├── OPENWRT_PORTING_ANALYSIS.md (this file)
├── device_tree_raw.txt         # Complete device tree information
├── uboot_environment.txt       # U-Boot and kernel boot parameters
├── gpio_pinmux_info.txt        # GPIO and LED configuration
├── switch_ethernet_config.txt  # Ethernet and network setup
└── additional_hardware_info.txt # I/O mappings and hardware details
```

## Conclusion

The AX3000HV2 (C30-401) presents a **viable candidate for OpenWrt porting** with strong hardware support foundation. The combination of existing Airoha EN7523 support, MT7916 wireless driver availability, and comprehensive hardware documentation provides a solid foundation for successful porting.

**Estimated Porting Effort**: Medium - requires device tree development and hardware-specific configuration but builds on existing platform support.

**Success Probability**: High - all critical hardware components have driver support in OpenWrt.