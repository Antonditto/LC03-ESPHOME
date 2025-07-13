# LC03-ESPHOME - RGB LED Strip Controller

ESPHome configuration for MagicHome LC03 WiFi RGB LED Strip Controller with IR Remote support.

## Features

- **Full RGB LED Strip Control** - Complete color control with brightness adjustment
- **IR Remote Support** - Control via included IR remote with all buttons mapped
- **Advanced Effects** - Multiple built-in effects including:
  - Random color transitions (slow/fast)
  - Pulse effects with configurable speed
  - Strobe effects
  - Christmas/Holiday themes
  - Alarm mode
  - Smooth transitions
- **Home Assistant Integration** - Full API support for home automation
- **WiFi Configuration** - Automatic fallback hotspot for easy setup
- **Web Interface** - Built-in web server for direct control
- **OTA Updates** - Over-the-air firmware updates
- **Status Monitoring** - WiFi signal strength monitoring

## Hardware

- **Device**: MagicHome LC03 WiFi RGB LED Controller
- **Chipset**: ESP8285 (ESP8266 variant)
- **GPIO Pins**:
  - GPIO4: IR Receiver (inverted)
  - GPIO5: Red PWM Output
  - GPIO12: Green PWM Output
  - GPIO13: Blue PWM Output

## Installation

1. **Prerequisites**:
   - ESPHome installed
   - Home Assistant (optional but recommended)

2. **Setup secrets file** (`secrets.yaml`):
   ```yaml
   wifi_ssid: "YourWiFiName"
   wifi_password: "YourWiFiPassword"
   ota_password: "YourOTAPassword"
   api_encryption_key: "YourAPIEncryptionKey"
   ```

3. **Compile and flash**:
   ```bash
   esphome compile led-strip.yaml
   esphome upload led-strip.yaml
   ```

## IR Remote Commands

The configuration supports a standard 44-key IR remote with the following mappings:

- **Power**: ON/OFF
- **Brightness**: Up/Down (5% increments)
- **Colors**: Red, Green, Blue, White + 16 preset colors
- **Effects**: Flash, Strobe, Fade, Smooth transitions

## Home Assistant Integration

After flashing, the device will automatically appear in Home Assistant if API is configured. You can:

- Control colors and brightness
- Switch between effects
- Monitor WiFi signal strength
- Use in automations and scenes

## Configuration

The configuration uses substitutions for easy customization:

- `device_name`: Network hostname
- `device_description`: Device description
- `device_id`: Internal ID for the light
- `friendly_name`: Display name in Home Assistant

## Support

For issues or questions, please refer to the ESPHome documentation or create an issue in this repository.
