# Hackintosh EFI for Nitro AN515-45 (Ryzen 5 5600H)


## Important Notice

Before using this EFI folder, you **must** generate your own system identifiers, including MLB, SystemSerialNumber, and SystemUUID.

### How to Generate Your Own System Identifiers

1. **Download GenSMBIOS:**
   - [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS)

2. **Run GenSMBIOS:**
   - Open GenSMBIOS and select option `1` to download the latest MacSerial.
   - Select option `3` to generate SMBIOS.

3. **Choose the Model:**
   - For this configuration, use `MacBookPro16,3`.

4. **Copy the Generated Values:**
   - Copy the generated `MLB`, `SystemSerialNumber`, and `SystemUUID` into the corresponding fields in the `config.plist`.

### Example

Replace the following fields in the `config.plist` with your generated values:

```xml
<key>PlatformInfo</key>
<dict>
	<key>Generic</key>
	<dict>
		<key>MLB</key>
		<string>YOUR_GENERATED_MLB</string>
		<key>SystemSerialNumber</key>
		<string>YOUR_GENERATED_SYSTEM_SERIAL_NUMBER</string>
		<key>SystemUUID</key>
		<string>YOUR_GENERATED_SYSTEM_UUID</string>
	</dict>
</dict>
```

## Usage

1. **Copy the EFI folder to your EFI partition.**
2. **Configure your BIOS settings as required.**
3. **Boot from the USB drive or the EFI partition on your hard drive.**

## Specifications

- **Model:** Nitro AN515-45
- **Processor:** AMD Ryzen 5 5600H (12) @ 3.30 GHz
- **Integrated GPU:** AMD Radeon Vega Series
- **Discrete GPU:** NVIDIA GeForce RTX 3060 Mobile / Max-Q // incompatible
- **Display:** 1920x1080 @ 144 Hz
- **RAM:** 16 GB 

## Files Included

- **ACPI:** Contains required DSDT and SSDT patches.
- **Kexts:** Essential kexts for hardware compatibility.
- **Drivers:** OpenCore drivers.
- **config.plist:** Configuration file for OpenCore.
  
## Kexts List

1. **AMDRyzenCPUPowerManagement.kext**
   - Provides power management for AMD Ryzen CPUs.

2. **AppleALC.kext**
   - Enables audio support for AppleHDA.

3. **AppleMCEReporterDisabler.kext**
   - Disables Apple MCE Reporter for non-Apple hardware.

4. **BrightnessKeys.kext**
   - Adds support for brightness keys on laptops.

5. **ECEnabler.kext**
   - Enables Embedded Controller for better compatibility.

6. **ForgedInvariant.kext**
   - Provides necessary invariants for the system.

7. **GenericUSBXHCI.kext**
   - Adds support for USB 3.0 controllers.

8. **HoRNDIS.kext**
   - Enables USB tethering.

9. **IntelMKLFixup.kext**
   - Fixes issues with Intel Math Kernel Library.

10. **Lilu.kext**
    - A general-purpose kext for patching macOS.

11. **NootedRed.kext**
    - Provides additional patches for AMD GPUs.

12. **NoTouchID.kext**
    - Disables Touch ID functionality.

13. **NVMeFix.kext**
    - Fixes issues with NVMe drives.

14. **RealtekRTL8111.kext**
    - Provides support for Realtek RTL8111 network controllers.

15. **RestrictEvents.kext**
    - Restricts certain events to improve compatibility.

16. **SMCAMDProcessor.kext**
    - Provides sensor support for AMD CPUs.

17. **SMCBatteryManager.kext**
    - Manages battery-related functions.

18. **SMCLightSensor.kext**
    - Enables light sensor functionality.

19. **SMCRadeonSensors.kext**
    - Provides sensor support for AMD Radeon GPUs.

20. **USBMap.kext**
    - Custom USB mapping for the laptop.

21. **VirtualSMC.kext**
    - Emulates SMC (System Management Controller) for macOS.

22. **VoodooI2C.kext**
    - Provides support for I2C trackpads and touchscreens.

23. **VoodooI2CHID.kext**
    - Companion kext for VoodooI2C to handle HID devices.

24. **VoodooPS2Controller.kext**
    - Adds support for PS/2 keyboards and trackpads.

25. **VoodooSMBus.kext**
    - Adds support for SMBus devices.

## Disclaimer

This EFI folder is provided as-is. Use it at your own risk. I am not responsible for any damage that may occur to your hardware or software.
