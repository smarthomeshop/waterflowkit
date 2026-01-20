# WaterFlowKit for Home Assistant / ESPHome

![WaterFlowKit Logo](images/waterflowkit-logo.png)

## 🌟 Professional Water Flow Monitoring

**WaterFlowKit** is a dedicated water flow monitoring solution with support for **dual flow sensors**, **water temperature sensing**, and **multiple connectivity options** including **WiFi, Ethernet, and Cloud sync**!

> 🎉 Built for Home Assistant users who need accurate water flow monitoring. 100% local, open-source, and designed for reliability!

### ⚡ What Makes Us Unique

| Feature                    | WaterFlowKit                                             |
| -------------------------- | -------------------------------------------------------- |
| 💧 **Dual Flow Sensors**   | Monitor **two water lines** simultaneously               |
| 🌡️ **Water Temperature**   | NTC temperature sensors for both flow inputs             |
| 🔧 **Dynamic Calibration** | Support for multiple flow sensor types with fine-tuning  |
| 🌐 **Triple Connectivity** | **WiFi**, **Ethernet** (V2), and **Cloud sync** options  |
| 🏠 **100% Local**          | No cloud required — runs entirely on your Home Assistant |
| ☁️ **Optional Cloud**      | Cloud sync available for users without Home Assistant    |

---

## Key Features

- **💧 Dual water monitoring**: Two independent flow sensor inputs with real-time flow rate (L/min) and total consumption (L)
- **🌡️ Water temperature**: NTC temperature sensors for both flow inputs
- **🌡️ Environment sensors**: Ambient temperature and humidity monitoring (HDC1080)
- **🔧 Multiple sensor support**: YF-B1/B7, YF-B5/B6, YF-B10, YF-DN40-S, YF-DN50-S with automatic calibration
- **📊 Fine-tune calibration**: Adjustable calibration percentage (50-150%) for precise measurements
- **🌐 WiFi + Ethernet**: Choose your preferred connectivity (Ethernet on V2)
- **☁️ Cloud sync**: Optional cloud connectivity for standalone operation
- **🔒 Fully local**: No cloud required — works offline with Home Assistant
- **📦 Pre-flashed**: Comes ready to use with WiFi firmware out of the box
- **💡 LED indicators**: RGB status LEDs for visual feedback

Learn more on our website: https://smarthomeshop.io

---

## Supported Flow Sensors

The WaterFlowKit supports multiple flow sensor types with automatic calibration:

| Sensor Model      | Pulses/Liter | Typical Use         |
| ----------------- | ------------ | ------------------- |
| **YF-B1 / YF-B7** | ~660         | Small pipes (1/2")  |
| **YF-B5 / YF-B6** | ~396         | Medium pipes (3/4") |
| **YF-B10**        | ~450         | General purpose     |
| **YF-DN40-S**     | ~27          | Large pipes (DN40)  |
| **YF-DN50-S**     | ~12          | Large pipes (DN50)  |

### Calibration

1. **Select your sensor type** in Home Assistant — the correct pulse factor is applied automatically
2. **Fine-tune with Calibration %** if needed:
   - Measure a known quantity (e.g., fill a 1L container)
   - If the sensor shows 0.9L, set calibration to **111%** (1.0 / 0.9 = 1.11)
   - Calibration range: 50% - 150%

> 💡 **Tip:** Flow sensors have a minimum flow rate (~1-2 L/min) before accurate measurement begins. For best calibration results, use higher flow rates.

---

## Hardware Versions

We have 2 hardware versions with multiple firmware variants:

| Feature                 | V1  | V2  |
| ----------------------- | --- | --- |
| WiFi                    | ✅  | ✅  |
| Ethernet                | ❌  | ✅  |
| Cloud Sync              | ✅  | ✅  |
| Flow Sensors            | 2x  | 2x  |
| NTC Temp Sensors        | 2x  | 2x  |
| HDC1080 (Temp/Humidity) | ✅  | ✅  |
| RGB LEDs                | ✅  | ✅  |

See the README in each version folder for detailed specifications.

---

## Getting Started

1. **Hardware**: Connect power via USB-C
2. **Connect**: All devices come **pre-flashed with WiFi firmware** out of the box
3. **Onboarding**: WiFi builds support captive portal and Improv for easy setup
4. **Configure**: Select your flow sensor type in Home Assistant
5. **Calibrate**: Fine-tune with a measured water quantity if needed

For full documentation see our quick start guide: https://smarthomeshop.io/quick-start-waterflowkit

---

## Firmware Variants

Each hardware version has multiple firmware options:

| Firmware           | Description                                         |
| ------------------ | --------------------------------------------------- |
| **WiFi**           | Standard Home Assistant integration via WiFi        |
| **Ethernet**       | Wired connection for reliability (V2 only)          |
| **WiFi Cloud**     | WiFi with cloud sync (works without Home Assistant) |
| **Ethernet Cloud** | Ethernet with cloud sync (V2 only)                  |

---

## Repository Layout

```
waterflowkit/
├── waterflowkit-v1/              # V1 ESPHome configurations
│   ├── base.yaml                 # Shared configuration
│   ├── wifi.yaml                 # WiFi connectivity
│   ├── cloud.yaml                # Cloud sync module
│   ├── waterflowkit-wifi.yaml    # WiFi firmware
│   └── waterflowkit-wifi-cloud.yaml  # WiFi + Cloud firmware
├── waterflowkit-v2/              # V2 ESPHome configurations
│   ├── base.yaml                 # Shared configuration
│   ├── wifi.yaml                 # WiFi connectivity
│   ├── eth.yaml                  # Ethernet connectivity
│   ├── cloud.yaml                # Cloud sync module
│   ├── waterflowkit-wifi.yaml    # WiFi firmware
│   ├── waterflowkit-ethernet.yaml    # Ethernet firmware
│   ├── waterflowkit-wifi-cloud.yaml  # WiFi + Cloud firmware
│   └── waterflowkit-ethernet-cloud.yaml  # Ethernet + Cloud firmware
├── .github/workflows/            # CI to build and publish firmware
└── images/
```

## Firmware Downloads

Pre-built firmware is available on the `gh-pages` branch:

**V1:**

- `waterflowkit-v1-wifi-manifest.json`
- `waterflowkit-v1-wifi-cloud-manifest.json`

**V2:**

- `waterflowkit-v2-wifi-manifest.json`
- `waterflowkit-v2-ethernet-manifest.json`
- `waterflowkit-v2-wifi-cloud-manifest.json`
- `waterflowkit-v2-ethernet-cloud-manifest.json`

## Installation via ESPHome Dashboard

**V1 WiFi:**

```yaml
packages:
  waterflowkit: github://smarthomeshop/waterflowkit/waterflowkit-v1/waterflowkit-wifi.yaml@main
```

**V2 WiFi:**

```yaml
packages:
  waterflowkit: github://smarthomeshop/waterflowkit/waterflowkit-v2/waterflowkit-wifi.yaml@main
```

**V2 Ethernet:**

```yaml
packages:
  waterflowkit: github://smarthomeshop/waterflowkit/waterflowkit-v2/waterflowkit-ethernet.yaml@main
```

## Contributing

PRs and issues are welcome. Please keep changes modular and follow ESPHome best practices.

## Support

- 🌐 Product info and guides: https://smarthomeshop.io
- 🛒 Store: https://smarthomeshop.io
- 💬 Community & support (Discord): https://smarthomeshop.io/discord

## License

This project is released under the MIT License (see `LICENSE`).
