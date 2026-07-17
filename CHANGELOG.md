# Changelog

All notable customer-facing firmware changes for WaterFlowKit are tracked in this file.

This changelog starts on 2026-04-01. Earlier firmware versions existed before that date, but they were not tracked in a customer-facing changelog.

## [Unreleased]

- Add customer-facing firmware notes here before merging a PR.

## [WaterFlowKit V1 1.12] - 2026-07-17


- Added a CPU temperature diagnostic sensor, also synced to SmartHomeShop Cloud, and updated the built-in web interface to version 3.



## [WaterFlowKit V2 2.12.0] - 2026-07-17


- Added a CPU temperature diagnostic sensor, also synced to SmartHomeShop Cloud, and updated the built-in web interface to version 3.



## [WaterFlowKit V1 1.11] - 2026-07-17


- Fixed cloud firmware restarting every 15 minutes when Home Assistant is not connected: the no-client reboot of the native API is now disabled on cloud firmware, so cloud-only setups run uninterrupted.

- The fallback setup hotspot now uses the password "waterflowkit" instead of being an open network.
- The setup portal now explains that choosing Ethernet installs the Ethernet firmware in the background and takes about two minutes before the network port works.


## [WaterFlowKit V2 2.11.0] - 2026-07-17


- Fixed cloud firmware restarting every 15 minutes when Home Assistant is not connected: the no-client reboot of the native API is now disabled on cloud firmware, so cloud-only setups run uninterrupted.

- The fallback setup hotspot now uses the password "waterflowkit" instead of being an open network.
- The setup portal now explains that choosing Ethernet installs the Ethernet firmware in the background and takes about two minutes before the network port works.


## [WaterFlowKit V1 1.10] - 2026-07-14


- Added the branded SmartHomeShop setup portal to WaterFlowKit V1 and V2 WiFi and cloud firmware: connecting to the fallback hotspot now opens a SmartHomeShop setup page to pick your WiFi network, choose your firmware variant and see next steps for Home Assistant or SmartHomeShop Cloud.
- WaterFlowKit V2 WiFi firmware can now switch itself to the Ethernet firmware from the setup portal: pick Ethernet during setup and the device installs the matching Ethernet variant over WiFi, after which you plug in the network cable. Flashing over USB-C via smarthomeshop.io/firmware remains available.
- Cloud firmware no longer blinks the status LED forever when the device is used without Home Assistant: the LED now blinks while offline and turns off once the device is connected.
- Faster cloud flow sync while water is actively flowing on WaterFlowKit V1.


## [WaterFlowKit V2 2.10.0] - 2026-07-14


- Added the branded SmartHomeShop setup portal to WaterFlowKit V1 and V2 WiFi and cloud firmware: connecting to the fallback hotspot now opens a SmartHomeShop setup page to pick your WiFi network, choose your firmware variant and see next steps for Home Assistant or SmartHomeShop Cloud.
- WaterFlowKit V2 WiFi firmware can now switch itself to the Ethernet firmware from the setup portal: pick Ethernet during setup and the device installs the matching Ethernet variant over WiFi, after which you plug in the network cable. Flashing over USB-C via smarthomeshop.io/firmware remains available.
- Cloud firmware no longer blinks the status LED forever when the device is used without Home Assistant: the LED now blinks while offline and turns off once the device is connected.
- Faster cloud flow sync while water is actively flowing on WaterFlowKit V1.


## [WaterFlowKit V2 2.9.0] - 2026-04-18


- Improved WaterFlowKit onboarding and adoption defaults so the public ESPHome configurations are easier to take control of through Made for ESPHome compatible flows.
- Reduced the V2 source-based cloud package footprint so WiFi cloud adoption builds fit again on ESP32-C6 devices with OTA partitions.


## [WaterFlowKit V2 2.7.0] - 2026-04-14

### Fixed

- The **Firmware Update** button now refreshes OTA metadata before installation, so changing **Firmware Type** to Ethernet no longer flashes the previously cached WiFi firmware.

### Changed

- Improved the **Firmware Update** button presentation and logging for clearer manual update feedback in Home Assistant and device logs.
- Added an extra pre-install log step so manual firmware switching is easier to trace when diagnosing OTA behavior.

## [WaterFlowKit V1 1.8] - 2026-04-14

### Fixed

- The **Firmware Update** button now refreshes OTA metadata before installation, so changing **Firmware Type** always installs the currently selected firmware variant.

### Changed

- Improved the **Firmware Update** button presentation and logging for clearer manual update feedback in Home Assistant and device logs.
- Added an extra pre-install log step so manual firmware switching is easier to trace when diagnosing OTA behavior.

## [WaterFlowKit V2 2.6.0] - 2026-04-14

### Added

- Added a dedicated **Firmware Update** button in Home Assistant for manual firmware installation.

### Changed

- Switching firmware variants now follows a clear two-step flow: choose **Firmware Type**, then press **Firmware Update**.

## [WaterFlowKit V1 1.7] - 2026-04-14

### Added

- Added a dedicated **Firmware Update** button in Home Assistant for manual firmware installation.

### Changed

- Switching firmware variants now follows a clear two-step flow: choose **Firmware Type**, then press **Firmware Update**.

## [WaterFlowKit V2 2.5.0] - 2026-04-01

### Changed

- No on-device behavior changes in this release.
- Improved the GitHub release publishing flow so firmware releases and version tags are created more reliably.

## [WaterFlowKit V1 1.6] - 2026-04-01

### Changed

- No on-device behavior changes in this release.
- Improved the GitHub release publishing flow so firmware releases and version tags are created more reliably.

## [WaterFlowKit V2 2.3.0] - 2026-04-01

### Added

- Customer-facing version history now lives in this repository.
- GitHub Releases will now be published for future firmware versions.

### Fixed

- Corrected the live water flow conversion for `pulse_counter` based sensors.

## [WaterFlowKit V1 1.4] - 2026-04-01

### Added

- Customer-facing version history now lives in this repository.
- GitHub Releases will now be published for future firmware versions.

### Fixed

- Corrected the live water flow conversion for `pulse_counter` based sensors.
