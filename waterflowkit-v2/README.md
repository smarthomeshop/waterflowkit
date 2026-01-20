# WaterFlowKit V2

Hardware version 2 of the WaterFlowKit.

## Specifications

- **MCU:** ESP32
- **Connectivity:** WiFi and Ethernet
- **Sensors:**
  - 2x Water flow sensor input (pulse counter)
  - 2x NTC temperature sensor input
  - HDC1080 temperature & humidity sensor
- **LED indicators:** RGB (red, green, blue)
- **I2C:** GPIO21 (SDA), GPIO22 (SCL)

## GPIO Pinout

| Function | GPIO |
|----------|------|
| Flow Sensor 1 | GPIO26 |
| Flow Sensor 2 | GPIO14 |
| NTC Sensor 1 | GPIO36 |
| NTC Sensor 2 | GPIO39 |
| LED Green | GPIO16 |
| LED Red | GPIO17 |
| LED Blue | GPIO04 |
| I2C SDA | GPIO21 |
| I2C SCL | GPIO22 |

## Supported Flow Sensors

The following flow sensors are supported with automatic calibration:

| Sensor Model | Pulses/Liter |
|--------------|--------------|
| YF-B1 / YF-B7 | ~660 |
| YF-B5 / YF-B6 | ~396 |
| YF-B10 | ~450 |
| YF-DN40-S | ~27 |
| YF-DN50-S | ~12 |

You can select your sensor type in Home Assistant and fine-tune calibration with the Calibration % setting (50-150%).

## Firmware Variants

- `waterflowkit-wifi.yaml` - WiFi version (Home Assistant integration)
- `waterflowkit-ethernet.yaml` - Ethernet version (Home Assistant integration)
- `waterflowkit-wifi-cloud.yaml` - WiFi version with Cloud sync (works without Home Assistant)
- `waterflowkit-ethernet-cloud.yaml` - Ethernet version with Cloud sync (works without Home Assistant)

## Installation

### Via ESPHome Web Installer

Go to [https://smarthomeshop.github.io/waterflowkit/](https://smarthomeshop.github.io/waterflowkit/) and follow the instructions.

### Via ESPHome Dashboard

**WiFi:**
```yaml
packages:
  waterflowkit: github://smarthomeshop/waterflowkit/waterflowkit-v2/waterflowkit-wifi.yaml@main
```

**Ethernet:**
```yaml
packages:
  waterflowkit: github://smarthomeshop/waterflowkit/waterflowkit-v2/waterflowkit-ethernet.yaml@main
```

**WiFi Cloud:**
```yaml
packages:
  waterflowkit: github://smarthomeshop/waterflowkit/waterflowkit-v2/waterflowkit-wifi-cloud.yaml@main
```

**Ethernet Cloud:**
```yaml
packages:
  waterflowkit: github://smarthomeshop/waterflowkit/waterflowkit-v2/waterflowkit-ethernet-cloud.yaml@main
```

## Configuration

After installation, you can configure the following settings in Home Assistant:

- **Flow1/Flow2 Sensor Type** - Select your connected flow sensor model
- **Flow1/Flow2 Calibration %** - Fine-tune calibration (100% = default, adjust based on measured vs actual flow)
- **Firmware Type** - Switch between WiFi, Ethernet, WiFi Cloud, or Ethernet Cloud firmware
