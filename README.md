# FlashBootloader_TMS570_GM

A specialized automotive flash bootloader for the Texas Instruments TMS570 microcontroller, tailored for General Motors (GM) SLP5 projects. This repository is organized for automotive integration, including diagnostics, security, CAN communication, and demo application support.

## Features

- **Platform Support:** TI TMS5700714PGEQQ1 MCU, built with TI Code Composer 4.9.5 toolchain.
- **GM SLP5 Bootloader:** Adapted for GM automotive firmware update and security.
- **Diagnostics:** ISO-15765 (UDS on CAN) protocol support.
- **Security:** HIS security module (CRC), demo RSA keys, and support for custom signed download containers.
- **Automotive BSW Structure:** Modular and maintainable Basic Software (BSW) layers.
- **Demo Application:** Example demo project and calibration header generation scripts.

## Project Structure (partial)

```
BSW/
  ├── FBL/           # Bootloader core, diagnostics, transport protocol, watchdog, versioning
  ├── SecMod/        # Security modules (CRC, crypto)
  └── Flash/Build/   # Flash driver scripts, linker configs, batch files
Demo/
  └── DemoAppl/Appl/ # Demo application, makefile, header generation scripts
Misc/
  └── HexView/       # Utility tools, disclaimer, hex/log examples
Doc/
  └── DeliveryInformation/ # Delivery documentation
```

> **Note:** Only a subset of files/folders is shown.  
> For the full structure, browse the repo.

## Documentation

- **Delivery Description:**  
  [Doc/DeliveryInformation/DeliveryDescription_CBD1400501.html](Doc/DeliveryInformation/DeliveryDescription_CBD1400501.html)
- **Disclaimer:**  
  [Misc/HexView/disclaimer.txt](Misc/HexView/disclaimer.txt)

## Getting Started

### Prerequisites

- **Hardware:** TI TMS5700714PGEQQ1 microcontroller
- **Compiler:** TI Code Composer Studio 4.9.5
- **Tools:** GNU Make, Windows batch script support

### Build Instructions

1. Navigate to the Flash build directory:
   ```
   cd BSW/Flash/Build
   ```
2. Use the provided batch scripts (e.g., `m.bat`) and Makefiles to build the bootloader.
3. For demo application usage and header generation, see batch files under `Demo/DemoAppl/Appl/ApplHdr_without_cal/`.

### Usage

- The bootloader can be programmed to the TMS570 using standard flashing/programming tools.
- UDS on CAN allows firmware update, diagnostics, and secure operations (signing, CRC, etc.).
- Security modules and demo keys are included for cryptographic and validation tasks.

## License

This project is intended for educational, research, or authorized automotive development use.  
Some modules are copyright © Vector Informatik.

## Disclaimer

Files and tools are provided “as is” and without warranty.  
See [Misc/HexView/disclaimer.txt](Misc/HexView/disclaimer.txt) for details.

---

*For more information, refer to code comments, scripts, and documentation files linked above. If you add new documentation, please place it in the `Doc/` directory and update this README.*
