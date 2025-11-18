# ESPHome Common Configuration Blocks

This repository contains a reusable set of **base ESPHome configuration
blocks** that can be included in most of your ESPHome devices.
The goal is to centralize shared configuration (logging, API, OTA,
syslog, WiFi diagnostics, uptime, time, etc.) so that every device
starts with the same reliable foundation.

By keeping these values in one place, you gain:

-   Consistent logging and debugging behavior
-   Unified OTA, API, syslog, and NTP configuration
-   Predefined diagnostics sensors available on every device
-   Lower maintenance burden when standards change
-   Cleaner device-specific YAML files

------------------------------------------------------------------------

## 📦 Included Features

This base config includes:

### 🔧 Substitutions

-   Default and max log levels
-   Syslog server IP
-   NTP settings
-   UART logger settings

### 📝 Logging

Configures: 

- log level
- syslog over UDP
- optional UART logging disable

### 🔌 Core Components

-   API
-   OTA
-   mDNS disabled
-   UDP target for syslog
-   SNTP time synchronization

### 🖲 Buttons

-   Restart button
-   Safe mode restart button

### 📡 Sensors

-   Uptime
-   WiFi RSSI
-   WiFi Channel
-   Binary status sensor

### 🧾 Text Sensors

-   WiFi SSID
-   IP address
-   MAC address

------------------------------------------------------------------------

## 🚀 How to Use This in an Existing ESPHome Device

### 1. Clone or reference this repo

    packages:
      common: github://bennydiamond/common_esphome_template/template.common.yaml

Or locally:

    packages:
      common: !include ../common_esphome_template/template.common.yaml

### 2. Override defaults if needed

    substitutions:
      default_syslog_server_ip: "192.168.0.200"
      default_log_level: INFO

### 4. Build and upload normally

All diagnostics and base config become automatically available.

------------------------------------------------------------------------

## 🔄 Updating the Common Config

Because all devices use `packages:`, updating `common.yaml` updates your
whole fleet automatically.

------------------------------------------------------------------------

## 🧩 Why This Exists

Most ESPHome devices duplicate the same boilerplate:

-   Logging
-   OTA
-   API
-   Time
-   Syslog
-   WiFi diagnostics

This repo removes duplication and keeps device YAMLs clean and
focused.
