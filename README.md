# ESP32-S3 AMOLED Digital Clock

A clean, flicker-free digital clock and date display written in Arduino for ESP32-S3 boards utilizing QSPI AMOLED displays and a real-time clock (RTC).

Designed with a classic aesthetic featuring a crisp white-on-black digital readout and optimized screen refreshing to prevent visual flicker.

---

## Hardware Target

* **Microcontroller / Display Board:** Waveshare ESP32-S3 Touch AMOLED 1.8" (or equivalent QSPI AMOLED development boards)
* **Display Driver:** CO5300 (via QSPI bus)
* **Real-Time Clock (RTC):** PCF85063

---

## Features

* **Classic Digital Style:** High-contrast pure black background (`0x0000`) with bright white time digits and a muted silver/gray date header.
* **Flicker-Free Updates:** Compares string states before redrawing, selectively clearing and updating only the necessary pixel coordinates rather than refreshing the whole screen every second.
* **Accurate Timekeeping:** Pulls continuous time and date data directly from the onboard PCF85063 RTC over I2C.

---

## Required Arduino Libraries

Make sure you have the following libraries installed via the Arduino IDE Library Manager:

1. [Arduino_GFX_Library](https://github.com/moononournation/Arduino_GFX)
2. [Arduino_DriveBus_Library](https://github.com/moononournation/Arduino_DriveBus)
3. [SensorLib](https://github.com/Xinyuan-LilyGO/SensorLib) (Handles the PCF85063 RTC driver)

---

## Configuration Note

This sketch relies on a local `pin_config.h` file supplied by your board's specific Arduino BSP (Board Support Package) or project configuration to map the QSPI bus lines (`LCD_CS`, `LCD_SCLK`, `LCD_SDIO0-3`) and I2C pins (`IIC_SDA`, `IIC_SCL`).

---

## Code Usage

1. Open the project in the Arduino IDE.
2. If you need to set the initial RTC time, uncomment the `rtc.setDateTime(...)` block in `setup()`, upload once to sync the clock, then comment it back out and re-upload.
3. Select your ESP32-S3 board target and upload the sketch.
