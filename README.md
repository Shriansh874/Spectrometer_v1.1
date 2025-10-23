# Spectrometer_v1.1

 
This repository contains the hardware design files, bill of materials, and firmware interfaces for the **Spectrometer_v1.1** board.

---

## Project Overview

Spectrometer_v1.1 is a compact embedded spectrometer designed around the **Nordic nRF52832 microcontroller** and **NIRONE sensor interface**, supporting environmental and optical sensing applications.  
The system integrates temperature, pressure, and humidity sensors, DAC control, power regulation, and wireless connectivity for portable data collection.

---

## Key Features

- **MCU:** Nordic nRF52832-QFAA (ARM Cortex-M4, BLE support)
- **Sensor Integration:**
  - BME280 (Temperature, Pressure, Humidity)
  - MCP4725 (12-bit DAC)
  - Optional NIRONE or external photodiode sensor interface
- **Power Management:**
  - TI TPS63020 buck-boost converter for 3.3 V regulation
  - MCP73831 Li-ion charging circuit with USB input
  - AP2112K LDO for stable output
- **Communication Interfaces:**
  - I2C (SDA/SCL)
  - USB (via CP2102 bridge)
  - SWD (for firmware flashing)
- **Connectivity:**
  - 2.45 GHz antenna matched to 50 Ω via π-network
- **Indicators:**
  - RGB LED (LTST-C19FD1WT)
  - Charge and system status LEDs

---

## Hardware Design

- **Schematic Files:**  
  `hardware/Spectrometer_v1.1.pdf`

- **Bill of Materials (BOM):**  
  `hardware/Spectrometer_v1.1_BOM.csv`

- **Notable Components:**
  - Power: TPS63020, AP2112K, MCP73831
  - MCU: nRF52832-QFAA
  - Sensors: BME280, MCP4725
  - USB Bridge: CP2102
  - RF Antenna: 2450AT45A100E (2.45 GHz ceramic)

---

## Firmware Overview

The firmware communicates with onboard sensors via I2C and manages BLE communication.

### Features
- Initialization of BME280 and DAC (MCP4725)
- BLE advertising for remote data collection
- Low-power mode during idle
- Battery voltage monitoring


