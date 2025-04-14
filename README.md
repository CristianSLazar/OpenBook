# Hardware Functionality

The OpenBook E-Reader is designed with a focus on simplicity, sustainability, and open-source flexibility. Below is a detailed breakdown of its hardware components, interfaces, communication specifications, processes, and power consumption considerations.

## Block Diagram

![Doesn't exist](https://docs.google.com/drawings/d/e/2PACX-1vShctzuF1lqpshVjldx9LcKVQY0B1pyAMw5UxdenfGo_w0oe6E8Shm842L3tUj0ByxdVggMVo3TpYYM/pub?w=1046&h=594)

## Bill of Materials

| Qty | Value | Device | Package | Parts | PURCHASE-URL | DATASHEET-URL |
| --- | ----- | ------ | ------- | ----- | ------------ | ------------- |
| 1 |  | ADAFRUIT_LEDCHIP-LED0603 | 0603 | CHG_LED | https://www.digikey.com/en/products/detail/w%C3%BCrth-elektronik/150060RS75000/4489901 | https://www.we-online.com/components/products/datasheet/150060RS75000.pdf |
| 1 | 0.1uF/50V | ESP32_WROVER_EAGLE-LTSPICE_C0402 | 0402 | EPD_C3 | https://www.digikey.com/en/products/detail/samsung-electro-mechanics/CL05B104KB5NNNC/11696318 | https://weblib.samsungsem.com/mlcc/mlcc-ec-data-sheet.do?partNumber=CL05B104KB5NNN |
| 1 | 0.47 | ESP32_WROVER_EAGLE-LTSPICE_RR0402 | 0402 | R3 | https://www.digikey.com/en/products/detail/panasonic-electronic-components/ERJ-2BQJR47X/5647384 | https://industrial.panasonic.com/cdbs/www-data/pdf/RDN0000/AOA0000C313.pdf |
| 1 | 100K | ESP32_WROVER_EAGLE-LTSPICE_RR0402 | 0402 | R_PWRUSB | https://www.digikey.com/en/products/detail/panasonic-electronic-components/ERJ-2RKF1003X/192081 | https://industrial.panasonic.com/cdbs/www-data/pdf/RDA0000/AOA0000C304.pdf |
| 8 | 100nF | ESP32_WROVER_EAGLE-LTSPICE_C0402 | 0402 | C1, C2, C3_USB, C5, C7, C8, C9, C_DELAY | https://www.digikey.com/en/products/detail/samsung-electro-mechanics/CL05B104KP5NNNC/3886660 | https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/609/CL05B104KP5NNNC_Spec.pdf |
| 1 | 100uF | RCL_CPOL-EUCT3528 | 3528 | C_TANT | https://ro.mouser.com/ProductDetail/KEMET/T491B107M006AT?qs=U312oeP%2FpiHOgyk6KO2m0g%3D%3D | https://ro.mouser.com/datasheet/2/447/KEM_T2005_T491-3316937.pdf
| 16 | 10K | ESP32_WROVER_EAGLE-LTSPICE_RR0402 | 0402 | R1, R1_PINH1, R1_PINH2, R2-PINH1, R2_PINH2, R4, R5, R6, R7, R8, R9, R10, R_BOOT, R_CHANGE, R_CL1, R_RESET | https://www.digikey.com/en/products/detail/panasonic-electronic-components/ERJ-2RKF1002X/192073 | https://industrial.panasonic.com/cdbs/www-data/pdf/RDA0000/AOA0000C304.pdf |
| 1 | 10uF | ESP32_WROVER_EAGLE-LTSPICE_C0402 | 0402 | C6 | https://www.digikey.com/en/products/detail/samsung-electro-mechanics/CL05A106MP5NUNC/3887108 | https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/2614/CL05A106MP5NUNC_Spec.pdf |
| 1 | 112A-TAAR-R03_ATTEND | 112A-TAAR-R03_ATTEND |  | J4 | https://www.digikey.ro/en/products/detail/attend-technology/112A-TAAR-R03/17633923 | https://www.attend.com.tw/data/download/file/112A-TAAR-R03_Spec.pdf |
| 1 | 15 | ESP32_WROVER_EAGLE-LTSPICE_RR0402 | 0402 | R_CAPACITOR | https://www.digikey.com/en/products/detail/panasonic-electronic-components/ERJ-2RKF15R0X/192142 | https://industrial.panasonic.com/cdbs/www-data/pdf/RDA0000/AOA0000C304.pdf |
| 1 | 1uF | ESP32_WROVER_EAGLE-LTSPICE_C0402 | 0402 | C4 | https://www.digikey.com/en/products/detail/samsung-electro-mechanics/CL05A105KO5NNNC/3886725 | https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/609/CL05A105KO5NNNC_Spec_5-2-19.pdf |
| 9 | 1uF/50V | ESP32_WROVER_EAGLE-LTSPICE_C0402 | 0402 | EPD_C1, EPD_C2, EPD_C4, EPD_C5, EPD_C6, EPD_C7, EPD_C8, EPD_C9, EPD_C10 | https://www.digikey.com/en/products/detail/murata-electronics/GRM155R61H105KE05D/13531808 | https://search.murata.co.jp/Ceramy/image/img/A01X/G101/ENG/GRM155R61H105KE05-01A.pdf |
| 1 | 2.2 | ESP32_WROVER_EAGLE-LTSPICE_RR0402 | 0402 | R2 | https://www.digikey.com/en/products/detail/panasonic-electronic-components/ERJ-2GEJ2R2X/282078 | https://api.pim.na.industrial.panasonic.com/file_stream/main/fileversion/1242 |
| 1 | 200 | ESP32_WROVER_EAGLE-LTSPICE_RR0402 | 0402 | R1_BAT | https://www.digikey.com/en/products/detail/panasonic-electronic-components/ERJ-2RKF2000X/192215 | https://industrial.panasonic.com/cdbs/www-data/pdf/RDA0000/AOA0000C304.pdf |
| 2 | 20V/4.2A/52mO/1.4W | ESP32_WROVER_SPARKFUN-DISCRETESEMI_MOSFET_PCH-DMG2305UX-7 |  | Q1, Q2 | https://www.digikey.ro/en/products/detail/diodes-incorporated/DMG2305UX-7/4340667 | https://www.diodes.com/assets/Datasheets/DMG2305UX.pdf |
| 1 | 2K | ESP32_WROVER_EAGLE-LTSPICE_RR0402 | 0402 | R2_BAT | https://www.digikey.com/en/products/detail/panasonic-electronic-components/ERJ-2RKF2001X/192194 | https://industrial.panasonic.com/cdbs/www-data/pdf/RDA0000/AOA0000C304.pdf |
| 5 | 4.7uF | ESP32_WROVER_EAGLE-LTSPICE_C0402 | 0402 | C1_BAT, C1_BAT1, C2_BAT, C2_BAT1, C4_USB | https://www.digikey.com/en/products/detail/samsung-electro-mechanics/CL05A475KQ5NRNC/3887139 | https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/41/CL05A475KQ5NRNC_Spec.pdf |
| 1 | 4.7uF/25V | ESP32_WROVER_EAGLE-LTSPICE_C0402 | 0402 | C3 | https://www.digikey.com/en/products/detail/murata-electronics/GRM155C61E475ME15D/16821133 | https://search.murata.co.jp/Ceramy/image/img/A01X/G101/ENG/GRM155C61E475ME15-01A.pdf |
| 2 | 5k1 | ESP32_WROVER_EAGLE-LTSPICE_RR0402 | 0402 | R1_USB, R2_USB | https://www.digikey.com/en/products/detail/panasonic-electronic-components/ERJ-2GEJ512X/147044 | https://api.pim.na.industrial.panasonic.com/file_stream/main/fileversion/1242 |
| 1 | 68uH | 744043680IND_4828-WE-TPC_WRE |  | L1 | https://www.digikey.de/en/products/detail/w%C3%BCrth-elektronik/744043680/1638515?srsltid=AfmBOoreM6iTR1zfidcAYx5855uFKN_t-1dK5Y4hJLHk64FUsesZV3qH | https://www.we-online.com/components/products/datasheet/744043680.pdf |
| 1 | BD5229G-TR | BD5229G-TR |  | U6 | https://www.digikey.com/en/products/detail/rohm-semiconductor/BD5229G-TR/658502 | https://www.rohm.com/datasheet?p=BD5229G&dist=Digi-key&media=referral&source=digi-key.com&campaign=Digi-key |
| 1 | BME688 | ESP32_WROVER_BME680_BME680 |  | U8 | https://www.digikey.ro/en/products/detail/bosch-sensortec/BME688/13681261 | https://www.bosch-sensortec.com/media/boschsensortec/downloads/datasheets/bst-bme688-ds000.pdf |
| 3 | BUTTON_CUSTOMV1 | BUTTON_CUSTOMV1 |  | BOOT_BUTTON, CHANGE_BUTTON, RESET_BUTTON |  |  |
| 1 | CPH3225A | CPH3225A |  | C_SUPERCAP | https://www.digikey.com/en/products/detail/seiko-instruments/CPH3225A/8692444 | https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/6537/rev05-CPHCPM.pdf |
| 1 | DS3231SN# | DS3231SN# |  | U3 | https://www.digikey.com/en/products/detail/analog-devices-inc-maxim-integrated/DS3231SN/1197576 | https://www.analog.com/media/en/technical-documentation/data-sheets/DS3231.pdf |
| 1 | ESP32-C6-WROOM-1-N8 | ESP32-C6-WROOM-1-N8 |  | U1 | https://www.digikey.com/en/products/detail/espressif-systems/ESP32-C6-WROOM-1-N8/17728866 | https://www.espressif.com/sites/default/files/documentation/esp32-c6-wroom-1_wroom-1u_datasheet_en.pdf |
| 1 | ESP32C6_VARISTORCN1812 | ESP32C6_VARISTORCN1812 |  | PFMF.050.1 | https://www.digikey.com/en/products/detail/schurter-inc/PFMF-050-2/1731348 | https://us.schurter.com/en/datasheet/typ_PFMF.pdf |
| 2 | ESP32_WROVER_AVX---SD0805S020S1R0 | ESP32_WROVER_AVX---SD0805S020S1R0 |  | D2, D7 | https://www.digikey.gr/en/products/detail/kyocera-avx/SD0805S020S1R0/3749517 | https://datasheets.kyocera-avx.com/schottky.pdf |
| 1 | FH34SRJ-24S-0.5SH_99_ | FH34SRJ-24S-0.5SH_99_ |  | J1 | https://www.digikey.com/en/products/detail/hirose-electric-co-ltd/FH34SRJ-24S-0-5SH-99/5132529 | https://www.hirose.com/en/product/document?clcode=CL0580-1253-0-99&productname=FH34SRJ-12S-0.5SH(99)&series=FH34SRJ&documenttype=SpecSheet&lang=en&documentid=0000414526 |
| 1 | MAX17048G+T10 | MAX17048G+T10 |  | U2 | https://www.digikey.com/en/products/detail/analog-devices-inc-maxim-integrated/MAX17048G-T10/3758921 | https://datasheets.maximintegrated.com/en/ds/MAX17048-MAX17049.pdf |
| 3 | MBR0530 | MBR0530 |  | D3, D4, D5 | https://eu.mouser.com/ProductDetail/Micro-Commercial-Components-MCC/MBR0530-TP?qs=KFo7JewZbUECRHkxGanrdg%3D%3D&srsltid=AfmBOopI5EY-Qmh6fu8QJtXckZ14Imu1WB2G5-0En3D3mZ6aqi4jmsQ2 | https://eu.mouser.com/datasheet/2/258/MBR0520_MBR0580_SOD123_-2492194.pdf |
| 1 | MCP73831 | ESP32_WROVER_SPARKFUN-IC-POWER_MCP73831 |  | U7 | https://www.digikey.com/en/products/detail/microchip-technology/MCP73831T-2ACI-OT/964301 | https://ww1.microchip.com/downloads/en/DeviceDoc/MCP73831-Family-Data-Sheet-DS20001984H.pdf |
| 6 | PGB1010603MR | PGB1010603MR |  | D6, D8, D9, D10, D11, D12 | https://www.digikey.com/en/products/detail/littelfuse-inc/PGB1010603MR/715755 | https://www.littelfuse.com/assetdocs/pulseguard-esd-suppressors-pgb1-datasheet?assetguid=8a337998-d54d-466b-be4e-dc5bcd1f9321 |
| 1 | QWIIC_RIGHT_ANGLE | QWIIC_CONNECTORJS-1MM |  | J3 | https://www.sparkfun.com/qwiic-jst-connector-smd-4-pin-horizontal.html | https://cdn.sparkfun.com/assets/parts/1/2/2/8/9/Qwiic_Connector_Datasheet.pdf |
| 1 | SAMACSYS_PARTS_USB4110-GF-A | SAMACSYS_PARTS_USB4110-GF-A |  | J2 | https://www.digikey.ro/en/products/detail/gct/USB4110-GF-A/10384547 | https://gct.co/files/specs/usb4110-spec.pdf?v=6b2a6292-70a5-4bd5-a7e5-0f3fe03e015f |
| 1 | SI1308EDL-T1-GE3 | SI1308EDL-T1-GE3 |  | Q3 | https://www.digikey.com/en/products/detail/vishay-siliconix/SI1308EDL-T1-GE3/4876435 | https://www.vishay.com/docs/63399/si1308edl.pdf |
| 1 | USBLC6-2SC6Y | USBLC6-2SC6Y |  | D1 | https://www.digikey.com/en/products/detail/stmicroelectronics/USBLC6-2SC6Y/2819177 | https://www.st.com/content/ccc/resource/technical/document/datasheet/group0/94/15/6c/58/ba/91/46/42/DM00055262/files/DM00055262.pdf/jcr:content/translations/en.DM00055262.pdf |
| 1 | W25Q512JVEIQ | W25Q512JVEIQ |  | U4 | https://www.digikey.com/en/products/detail/winbond-electronics/W25Q512JVEIQ/10244706 | https://www.winbond.com/resource-files/W25Q512JV%20SPI%20RevB%2006252019%20KMS.pdf |
| 1 | XC6220A331MR-G | XC6220A331MR-G |  | U5 | https://www.digikey.in/en/products/detail/torex-semiconductor-ltd/XC6220A331MR-G/10165775 | https://product.torexsemi.com/system/files/series/xc6220.pdf |
| 1 | | CELLEVIA BATTERIES LP584174 | | https://www.tme.eu/en/details/accu-lp584174_cl/rechargeable-batteries/cellevia-batteries/l584174/ | https://www.tme.eu/Document/e0683d8c34e6d878124489f71bffb6ee/cel0014.pdf
| 1 | | Waveshare 7.5inch e-Paper V2 | | https://www.waveshare.com/7.5inch-e-paper-hat.htm | https://files.waveshare.com/upload/6/60/7.5inch_e-Paper_V2_Specification.pdf
| 1 | | Casing | | | |

## Core Hardware Components

1. **Microcontroller**

    * Model: ESP32-C6-WROOM-1 (or equivalent) for its integrated Wi-Fi 6, BLE 5, and ample processing power.

    * Functionality: Manages display rendering, input handling, sensor data processing, and communication.

    * Interfaces: Communicates with peripherals via SPI, I²C, UART, and GPIO.

2. **Display**

    * Model: Waveshare WSH-13187 7.5inch e-Paper display.

    * Resolution: 800x480.

    * Interface: SPI (Serial Peripheral Interface).

    * Functionality:

        * Provides a paper-like reading experience.

        * Only consumes power when changing content.

3. **Sensors (for environmental monitoring)**

    * Interface: All sensors communicate via I²C bus (reduces pin usage).

    * Process: Sensor readings are periodically captured and displayed for user awareness.

    | Sensor Type | Function | Model | Interface | Power Consumption |
    | ----------- | -------- | ------------ | --------- | ----------------- |
    | Temperature | Measures ambient temperature | Bosch BME688 | I²C | ~1.8mA @ 3.3V |
    | Humidity | Measures relative humidity | Bosch BME688 | I²C | ~1.8mA @ 3.3V |
    | Pressure | Measures atmospheric pressure | Bosch BMP288 | I²C | ~2.7mA @ 3.3V |
    | Air Quality | Estimates VOC and pollution levels | Bosch BME688 | I²C | ~12mA @ 3.3V |

4. **Buttons & User Interface**

    * Buttons: Three physical buttons for page navigation and menu control.

    * Interface: GPIO (General Purpose Input/Output).

    * Functionality:

        * Provides a tactile, distraction-free experience.

        * Reduces reliance on touchscreen power consumption.

5. **Connectivity**

    * Wi-Fi Module: Integrated in MCU.

        * Interface: SPI or UART.

        * Functionality: Enables e-book downloads, firmware updates, and online features.

    * USB-C Port:

        * Functions:

            * Charging (5V/1A).

            * Data transfer for sideloading books.

        * Interface: USB 2.0.

6. **Storage**

    * SD Memory Card Connector: Attend Tech 112A-TAAR-R03.

        * Interface: SPI.

    
    * External Flash: MAX17048G.

        * Interface: SPI.

    * Functionality: Stores books, firmware, and settings.

7. **Power System**

    * Battery: 2500mAh Lithium-Polymer battery.

    * Charging Interface: USB-C, 5V/1A.

    * Battery Management:

        * Uses MCP73831 Power Management IC.

        * Includes overcharge, over-discharge, and short-circuit protection.

    * Expected Battery Life: At least one week per charge.

## Communication and Data Flow

### Communication Interfaces

| Component | Interface | Function |
| --------- | ---------| -------- |
| Microcontroller - Display | SPI | Transfers image data to the e-paper screen |
| Microcontroller - Sensors | I²C | Reads environmental sensor data |
| Microcontroller - Storage | SPI | Reads/writes e-books and firmware |
| Microcontroller - USB-C | USB 2.0 | Data transfer & charging |

## Power Consumption Estimation

| Component | Active Power (mW) | Sleep Power (mW) | Notes |
| --------- | ----------------- | ---------------- | ----- |
| Microcontroller | 50–150mW | 10mW | Depends on task |
| E-Paper Display | ~500mW (refresh) | ~0mW | Only consumes power during refresh |
| Wi-Fi Module | ~250mW | ~5mW | Wi-Fi off in sleep mode |
| Temperature Sensor | 1.8mW | 0.1mW | I²C bus shared |
| Humidity Sensor | 1.8mW | 0.1mW | I²C bus shared |
| Pressure Sensor | 2.7mW | 0.1mW | I²C bus shared |
| Air Quality Sensor | 12mW | 1mW | Runs periodic checks |
| Physical Buttons | 0mW | 0mW | Uses GPIO interrupts |
| USB-C Charging | ~5W | - | Only active when charging |

### Estimated Battery Life

**Average Power Consumption**: ~200mW (normal reading mode).

**Battery Capacity**: ~2500mAh (~9.25Wh @ 3.7V).

**Runtime Calculation**:

* 9.25Wh0.2W≈46 hours of active reading
* 0.2W9.25Wh​≈46 hours of active reading

This translates to 1–2 weeks per charge, assuming ~3–4 hours of daily reading.

## Additional Considerations

* Regulatory Compliance:

    FCC (wireless compliance), CE (safety), RoHS (environmental standards).

* Thermal Design:

    Passive cooling (no fans required due to low power usage).

* Firmware Update Process:

    * OTA (Over-the-Air) updates via Wi-Fi.

    * USB sideloading as a fallback.

* Modular Expansion Possibilities:

    * Future support for Bluetooth (e.g., syncing annotations).

    * Open GPIO pins for DIY modifications.

## Microcontroller Pin Assignments

### SPI (Serial Peripheral Interface) – For Display and Storage

SPI is used for fast data transmission between the MCU and E-paper display and Flash storage.

| Component | Signal Name | Pin Number | Description |
| --------- | ------------ | ---------- | ----------- |
| E-Paper Display | MOSI | GPIO 7 | Master Out, transmits image data |
| | MISO | GPIO 2 | Master In, not used (one-way communication) |
| | SCK | GPIO 6 | Clock signal for SPI |
| | EPD_CS | GPIO 10 | Chip Select for E-paper display |
| | EPD_BUSY | GPIO 3 | Display busy signal (high = busy) |
| | EPD_RST | GPIO 23 | Hardware reset for the display |
| | EDP_DC | GPIO 5 | Serial communication Data/Command input
| SD Card |	MOSI | GPIO 7 | Shared MOSI pin |
| | MISO | GPIO 2 | Shared MISO pin |
| | SCK | GPIO 6 | Shared Clock pin |
| | SS_SD | GPIO 16 | Chip Select for SD Card |
| External Flash | MOSI | GPIO 7 | Shared MOSI pin |
| | MISO | GPIO 2 | Shared MISO pin |
| | SCK | GPIO 6 | Shared Clock pin |
| | FLASH_CS | GPIO 11 | Chip Select for external flash |

**Note**: The same SPI bus is shared between the e-paper display and storage, but they have separate chip select (CS) lines.

## I²C (Inter-Integrated Circuit) - For Sensors

I²C is used for low-power, two-wire communication with environmental sensors.

| Component | Signal Name | Pin Number | Description |
| --------- | ------------ | ---------- | ----------- |
| Environmental Sensor | SDA | GPIO 21 | Data line |
| | SCL | GPIO 22 | Clock line |

**Note**: All sensors share the same I²C bus (SDA & SCL), differentiated by unique I²C addresses.

### UART (Universal Asynchronous Receiver-Transmitter) – For Communication Modules

UART is used for serial debugging.

| Signal Name | Pin Number | Description |
| ------------ | ---------- | ----------- |
| TX | GPIO 16 | Debug TX output |
| RX | GPIO 17 | Debug RX input |

### GPIO (General Purpose Input/Output) – For Buttons & LEDs

GPIO pins are used for physical buttons, status LEDs, and interrupts.

| Component | Signal Name | Pin Number | Description |
| --------- | ----------- | ---------- | ----------- |
| I/O (Boot) Button | IO/BOOT | GPIO 9 | Button press input |
| Reset Button | RESET | EN | Button press input |
| I/O (Change) Button | IO/CHANGE | GPIO 15 | Button press input |

### RTC pins

| Component | Signal Name | Pin Number | Description |
| --------- | ----------- | ---------- | ----------- |
| Real Time Clock | INT_RTC | GPIO 0 | Interrupt line |
| | RTC_RST | GPIO 18 | Clock reset line |
| | 32KHZ | GPIO 1| Clock line |

### USB data pins

| Component | Signal Name | Pin Number | Description |
| --------- | ----------- | ---------- | ----------- |
| USB Connector | USB_D+ | GPIO 13 | Positive differential data line |
| USB Connector | USB_D- | GPIO 12 | Negative differential data line |

## Conclusion

The OpenBook E-Reader is a well-optimized, low-power device that leverages an efficient microcontroller, e-paper display, and integrated environmental sensors. By utilizing SPI, I²C, and GPIO interfaces, it ensures a simple yet powerful design with extended battery life, modularity, and open-source flexibility. The estimated power consumption aligns well with the goal of at least one week of reading per charge, making it a compelling alternative to mainstream e-readers.

## Notes

* Content of README.md adapted from generated response by ChatGPT
* Power consumption estimations and calculations generated by ChatGPT
