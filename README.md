# DIY CNC Router

🚧 **Status: work in progress** - mechanical design and electronics design finished, controller PCB in production, firmware in progress.

A from-scratch CNC router build: mechanical design in CAD, a custom ESP32-based controller board, and FluidNC firmware.

## Table of Contents
- [Overview](#overview)
- [Mechanics](#mechanics)
- [Electronics / Controller](#electronics--controller)
- [Firmware](#firmware)
- [Problems Encountered & Solutions](#problems-encountered--solutions)
- [Photos](#photos)
- [Roadmap](#roadmap)
- [License](#license)

## Overview

[TODO: 2-3 sentences - working area dimensions, intended use (wood/PCB), what sets this build apart from off-the-shelf kits]

## Mechanics

- Full 3D assembly designed in **Fusion 360** - complete
- Printed parts in **PETG** on a **Bambu Lab P2S Combo**
- [TODO: rails/linear guides, leadscrews/ball screws, X/Y/Z travel dimensions]

## Electronics / Controller

Custom PCB (KiCad) integrating:
- **ESP32** as the main controller
- **4x TMC2209** — stepper motor drivers
- Firmware: **FluidNC**

[TODO: exact ESP32 variant (WROOM/WROVER/S3?), buck converter model, system supply voltage, stepper motor type/current rating]

### BOM (Bill of Materials)
| Component | Model | Qty |
|---|---|---|
| Microcontroller | ESP32 DevKit V1 | 1 |
| Stepper driver | TMC2209 | 4 |
| Stepper motors | 17HS4401 | 3 |

## Firmware

Based on FluidNC. [TODO: link/config.yaml file, FluidNC version, any modifications]

## Problems Encountered & Solutions

A short log of real issues hit during design — often more interesting than the finished result:

- **GPIO pin assignment** — several ESP32 pins are input-only or strapping pins, which limited the freedom to route control signals and required reworking part of the pin mapping.
- **EN_PWM on GPIO39** — schematic review caught that the EN_PWM signal was assigned to an input-only pin (GPIO39), which meant it couldn't function correctly as an output. [TODO: describe the fix]
- **Unmapped 0–10V signal** — schematic review also found that the analog 0–10V signal had no input assigned. [TODO: describe the fix]

## Photos

[TODO: add photos/renders — `![description](path/to/image.jpg)`]

## Roadmap

- [x] Mechanical assembly in Fusion 360
- [x] Controller PCB schematic and layout in KiCad
- [ ] PCB fabrication and assembly
- [ ] FluidNC firmware bring-up
- [ ] First test cut

## License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.
