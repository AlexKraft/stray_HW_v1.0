
### **Hardware Deep Dive: The 'Stray' v1 Prototype (and all its quirks)**

# Source Files & Final Notes

The PCB source files were created in [DipTrace](https://diptrace.com/ua/). It's a free-for-small-projects tool, but it's not very common, so you'll have to download it if you want to poke around.

## Hardware (v1 Prototype)

The current version (`v1`) is a custom-built prototype. It's fully functional but has several quirks and "overkill" components (like the audio codec) based on its original design.

For a **full deep-dive**, including the design story, schematics, and all the quirks, please [read the detailed log post on Hackaday.io](https://hackaday.io/project/204294-stray/log/244166-1-hardware-deep-dive-the-stray-v1-prototype-and-all-its-quirks).

### Key Specifications

| Component | Specification | Notes |
| :--- | :--- | :--- |
| **MCU** | ESP32-WROOM | External IPX Antenna |
| **Audio Codec** | TLV320AIC3120 | I2C Control, I2S Data |
| **Display** | 1.54" SPI LCD | ST7789, 240x240, PWM Backlight |
| **Encoder** | AS5601 (Magnetic) | Read via I2C |
| **Keypad** | 7-button via 74HC164 | PTT & Power are separate GPIOs |
| **Power** | 4000mAh LiPo | MAX1811 for charging (MicroUSB) |

### Hardware Abstraction & Quirks

* **Adaptation:** The code is structured with a **Board Support Package (BSP)** layer (`/bsp`). To use your *own* hardware, you only need to modify the functions in `bsp/` to match your pinout.
* **Flashing:** This v1 prototype requires an **external USB-to-UART converter** for flashing. The MicroUSB port is for **charging only**.
* **Source Files:** Hardware source files (DipTrace), schematics, and Gerber files are available in the `/hardware` directory of this repo.

### DOC folder
I will fill in as needed.

