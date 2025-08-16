# AX3000HV2 Router - OpenWrt Device Development Files

## Device Information
- **Model**: AX3000HV2 (Airoha EN7523 SoC based router)
- **Current Firmware**: OpenWrt 21.02.1 r16325-88151b8303  
- **Hardware Version**: C30-401
- **MAC Address**: 20:BE:B4:XX:XX:XX
- **Chipset**: MT7916 WiFi chipset

## Key Hardware Details
- **SoC**: Airoha EN7523
- **WiFi**: MT7916 dual-band (2.4GHz + 5GHz)
- **Bands**: 2-band configuration
  - 2.4GHz: HE40 mode (WiFi 6)
  - 5GHz: HE160 mode (WiFi 6)
- **Antennas**: 2x2 MIMO on both bands
- **Memory**: Available in system info files
- **Flash**: MTD partitions documented

## Extracted Files Overview

### System Information
- `cpuinfo.txt` - CPU architecture and features
- `system_info.txt` - Memory info, kernel version, system details
- `storage_partitions.txt` - MTD partitions, disk usage, partition table
- `dmesg_boot.txt` - Boot messages and hardware initialization

### Configuration Files
- `config_network.txt` - Network interface configuration  
- `config_wireless.txt` - WiFi radio and interface settings
- `config_system.txt` - System settings and hostname
- `config_dhcp.txt` - DHCP and DNS configuration
- `config_firewall.txt` - Firewall rules and zones

### Wireless Configuration
- `etc/Wireless/` directory extracted with:
  - `RT2860AP/RT2860AP.dat` - 2.4GHz radio configuration
  - `RT2860AP_AC/RT2860AP.dat` - 5GHz radio configuration  
  - `l1profile.dat` - Wireless profile configuration
  - Various other wireless config files

### Kernel and Hardware
- `kernel_modules.txt` - Loaded kernel modules (lsmod output)
- `kernel_details.txt` - Kernel command line, I/O memory map, interrupts
- `device_tree_paths.txt` - Device tree and hardware paths
- `kernel_modules_list.txt` - Available kernel modules and device tree status

### Partition and Storage
- `flash_dump_sample.txt` - Sample hexdump of flash partitions
- `filesystem_info.txt` - Device nodes, MTD devices, mounted filesystems

## OpenWrt Development Notes
- Device runs OpenWrt 21.02.1 successfully
- MT7916 wireless driver functional
- Airoha EN7523 SoC supported
- All standard OpenWrt tools available (UCI, LuCI, etc.)
- Package manager (opkg) working with 8,705+ packages available

## Files Suitable for Device Definition
The extracted files contain all necessary information for creating an OpenWrt device definition including:
- Hardware specifications and partitioning
- Wireless driver configuration  
- Kernel module requirements
- Boot process details
- Device tree structure (if available)


## Factory Reset Info
- **Default IP**: 192.168.1.1
- **Default SSID**: FPT Telecom-XXXX
- **Default WiFi Password**: XXXXXXXX  
- **Default Login**: admin/XXXXXXXXXX

---
*Files extracted on: $(date)*
*Purpose: OpenWrt device development and definition creation*
