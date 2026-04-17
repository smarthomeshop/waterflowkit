# WaterFlowKit for Home Assistant / ESPHome

![WaterFlowKit](images/waterflowkit-product-shop.png)

WaterFlowKit is an ESPHome-based water flow monitor for Home Assistant. It measures flow rate, total consumption, and water temperature from supported pulse-based flow sensors, with local operation and optional cloud-sync firmware variants.

Product page: https://smarthomeshop.io/waterflowkit

## How It Works

WaterFlowKit reads pulse signals from supported Hall-effect flow sensors and converts them into flow rate and total consumption. Each input can also use an NTC sensor for water temperature monitoring.

## Key Features

- Real-time flow rate and total water consumption
- Water temperature support per flow input
- Temperature and humidity sensing with HDC1080
- Support for multiple YF-series flow sensors with calibration options
- WiFi and Ethernet firmware depending on hardware version
- Optional cloud-sync variants
- Fully local operation by default

## Hardware Versions

| Version | Chip | Connectivity | Flow Inputs |
|---------|------|--------------|-------------|
| V1 | ESP32 | WiFi | 2 |
| V2 | ESP32-C6 | WiFi and Ethernet | 4 |

## Variants

We publish firmware for two hardware revisions. Each customer-facing variant has its own YAML file and matching Web Tools manifest.

| Hardware | Variant | Description |
|----------|---------|-------------|
| V1 (ESP32) | WiFi (local) | Standard local WiFi connectivity |
| V1 (ESP32) | WiFi + SmartHomeShop App (cloud) | WiFi with SmartHomeShop App cloud sync |
| V2 (ESP32-C6) | WiFi (local) | Local WiFi with Improv BLE and Improv Serial |
| V2 (ESP32-C6) | Ethernet (local) | Standard wired local connectivity |
| V2 (ESP32-C6) | WiFi + SmartHomeShop App (cloud) | WiFi with SmartHomeShop App cloud sync |
| V2 (ESP32-C6) | Ethernet + SmartHomeShop App (cloud) | Ethernet with SmartHomeShop App cloud sync |

## Supported Flow Sensors

| Sensor Model | Pulses per Liter | Typical Use |
|--------------|------------------|-------------|
| YF-B1 / YF-B7 | About 660 | Small pipes (1/2") |
| YF-B5 / YF-B6 | About 396 | Medium pipes (3/4") |
| YF-B10 | About 450 | General purpose |
| YF-DN40-S | About 27 | Large pipes (DN40) |
| YF-DN50-S | About 12 | Large pipes (DN50) |

## Sensors

| Sensor | Description |
|--------|-------------|
| Flow1/Flow2 Current Usage | Flow rate in liters per minute |
| Flow1/Flow2 Total Consumption | Cumulative water usage |
| Flow1/Flow2 Water Temperature | Water temperature |
| Temperature | Environment temperature |
| Humidity | Environment humidity |
| WiFi Signal | WiFi signal strength |
| Uptime | Device uptime |

## Getting Started

1. Connect power and wire the flow sensors.
2. Flash the desired firmware with the web flasher or ESPHome CLI.
3. If WiFi is not configured yet, connect to the fallback hotspot.
4. Use Improv BLE or Improv Serial where supported.
5. Select the flow sensor type in Home Assistant and calibrate if needed.

Web flasher: https://smarthomeshop.io/firmware
Quick start guide: https://smarthomeshop.io/quick-start-waterflowkit

## Version History

- Customer-facing release notes: [CHANGELOG.md](CHANGELOG.md)
- GitHub Releases: https://github.com/smarthomeshop/waterflowkit/releases

## Repository Layout

```text
waterflowkit/
├── waterflowkit-v1/        # V1 ESPHome configurations
│   ├── base.yaml           # Shared configuration
│   ├── waterflowkit-wifi.yaml
│   └── waterflowkit-wifi-cloud.yaml
├── waterflowkit-v2/        # V2 ESPHome configurations
│   ├── base.yaml
│   ├── waterflowkit-wifi.yaml
│   ├── waterflowkit-ethernet.yaml
│   ├── waterflowkit-wifi-cloud.yaml
│   └── waterflowkit-ethernet-cloud.yaml
├── .github/workflows/      # Build and release automation
├── CHANGELOG.md            # Customer-facing firmware notes
└── images/
```

## Firmware Downloads

Pre-built firmware manifests are published on the `gh-pages` branch.

- V1 WiFi (local): `waterflowkit-v1-wifi-manifest.json`
- V1 WiFi + SmartHomeShop App (cloud): `waterflowkit-v1-wifi-cloud-manifest.json`
- V2 WiFi (local): `waterflowkit-v2-wifi-manifest.json`
- V2 Ethernet (local): `waterflowkit-v2-ethernet-manifest.json`
- V2 WiFi + SmartHomeShop App (cloud): `waterflowkit-v2-wifi-cloud-manifest.json`
- V2 Ethernet + SmartHomeShop App (cloud): `waterflowkit-v2-ethernet-cloud-manifest.json`

## Contributing

PRs and issues are welcome. Please keep changes modular and follow ESPHome best practices.

## Support

- Product info and guides: https://smarthomeshop.io/waterflowkit
- Store: https://smarthomeshop.io
- Community and support: https://smarthomeshop.io/discord

## License

This project is released under the CC BY-NC 4.0 license.

![WaterFlowKit](images/waterflowkit-whatsinthebox-shop.png)
