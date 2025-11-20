<div align="center">

# BR Equipment Scripts

**Production Automation Scripts for Blue Robotics Manufacturing Equipment**

[![license: MIT](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](LICENSE)

</div>

---

## Overview

Collection of `.breq` (BR Equipment) automation scripts for controlling Blue Robotics manufacturing equipment. These scripts coordinate multiple devices for production tasks like assembly, testing, and quality control.

Scripts are organized by device folder (e.g., `pressboi/`, `fillhead/`, `gantry/`).

**Used with:** [BR Equipment Control App](https://github.com/bluerobotics/br-equipment-control-app)

---

## Usage

### 1. Install the Control App

Download the [BR Equipment Control App](https://github.com/bluerobotics/br-equipment-control-app/releases/latest) for your platform.

### 2. Open a Script

- **File → Open** or **Ctrl+O**
- Select a `.breq` script from this repository
- The app provides syntax highlighting and validation

### 3. Connect Your Devices

- Devices are auto-discovered over USB or Ethernet
- Check device status in the device panel

### 4. Run the Script

- **Click "Run"** or press **F5**
- Use **Step** mode for debugging
- Scripts can be paused/resumed/stopped at any time

---

## Script Format

`.breq` scripts use a simple text-based format:

```breq
# This is a comment

# Device commands
pressboi.home
pressboi.move_abs 100 50

# Built-in commands
wait 5
cycle 10
    gantry.move_x 10
    wait 1

# Data logging
queue_for_logging
    pressboi.position_mm
    pressboi.force_n

start_logging "test.csv" pressboi
wait 30
stop_logging
```

See the [scripting documentation](https://github.com/bluerobotics/br-equipment-control-app#6-scripting) for full syntax reference.

---

<div align="center">

Made with 💙 by the Blue Robotics team

**[bluerobotics.com](https://bluerobotics.com)**

</div>

