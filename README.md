# ESP32-S3 AMOLED Examples

A collection of Arduino sketches and examples for the **Waveshare ESP32-S3 Touch AMOLED 1.8"** (and compatible QSPI AMOLED development boards), utilizing high-performance graphics libraries and onboard peripherals.

---

## Hardware Target

* **Microcontroller / Display Board:** Waveshare ESP32-S3 Touch AMOLED 1.8"
* **Display Driver:** CO5300 (via QSPI bus)
* **Real-Time Clock (RTC):** PCF85063

---

## Included Examples

### 1. Classic Digital Clock (`/digital-clock`)
A clean, flicker-free digital clock and date display.
* **Aesthetic:** High-contrast pure black background (`0x0000`) with bright white time digits and a muted silver/gray date header.
* **Performance:** Uses string-comparison logic to selectively redraw only the text areas that change every second, preventing full-screen flicker.
* **Time Source:** Pulls live time and date data from the onboard PCF85063 RTC over I2C.

*(More examples coming soon...)*

---

## Required Arduino Libraries

Ensure you have the following libraries installed via the Arduino IDE Library Manager:

1. [Arduino_GFX_Library](https://github.com/moononournation/Arduino_GFX)
2. [Arduino_DriveBus_Library](https://github.com/moononournation/Arduino_DriveBus)
3. [SensorLib](https://github.com/Xinyuan-LilyGO/SensorLib) (Handles the PCF85063 RTC driver)

---

## Board Configuration

These sketches rely on a local `pin_config.h` file (typically provided by your board's specific Arduino BSP) to map the QSPI display lines (`LCD_CS`, `LCD_SCLK`, `LCD_SDIO0-3`) and I2C lines (`IIC_SDA`, `IIC_SCL`). Make sure your board package is up to date in the Arduino IDE.

---

## License

This project is open-source and available under the MIT License.
