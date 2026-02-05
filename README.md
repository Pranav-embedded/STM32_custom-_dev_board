# STM32F103C8T6 Custom Development Board

Custom designed **STM32F103C8T6 minimum system board** with USB interface, onboard 3.3V regulation, boot configuration, and SWD programming support.

Designed using **KiCad 9.0.7** with full DRC clearance and industry-standard PCB layout practices.

---

# Project Overview

This project is a compact 2-layer custom development board built around the **STM32F103C8T6 (ARM Cortex-M3)** microcontroller.

### Objectives:

- Design a production-ready STM32 minimum system  
- Implement clean and stable 3.3V power architecture  
- Enable USB device communication  
- Apply professional PCB layout practices  
- Validate design using ERC & DRC  

This board is intended for embedded development, experimentation, and scalable application integration.

---

# Microcontroller

**MCU:** STM32F103C8T6  
- ARM Cortex-M3  
- 72 MHz  
- 64 KB Flash  
- 20 KB SRAM  
- USB 2.0 Full Speed  
- SWD Debug Interface  

---

# Power Architecture

### Input
- USB VBUS (5V)

### Regulation
- AMS1117-3.3 LDO regulator
- Output: +3.3V
- +3.3VA isolated using Ferrite Bead (FB1)

### Decoupling Strategy
- Multiple 100nF ceramic capacitors placed close to VDD pins
- 10µF and 22µF bulk capacitors for voltage stability
- Analog filtering section for noise-sensitive circuits

### Design Considerations
- Short return current paths
- Local decoupling near each power pin
- Ferrite bead isolation between digital and analog domains
- Ground plane on bottom layer for stable reference

---

# Clock System

- 16 MHz external crystal (HSE)
- Proper load capacitors (10pF)
- Short, symmetric routing to reduce noise and jitter
- Minimal loop area around crystal network

---

# Boot Configuration

- BOOT0 selectable via SPDT switch
- Pull-down resistor ensures stable default boot
- Supports:
  - Flash boot mode
  - System bootloader mode

---

# USB Interface

- USB Type-C connector (USB 2.0)
- D+ and D− routed carefully
- Pull-up resistor for USB detection
- Short routing with proper ground reference
- Layout kept compact to reduce signal distortion

---

# Programming & Debug

4-Pin SWD Header:
- SWCLK
- SWDIO
- 3.3V
- GND

Compatible with:
- ST-Link
- J-Link

---

# PCB Specifications
- Form Factor: Compact Embedded Module
- Board Size: 44.48 mm × 18.99 mm
- 2 Layer PCB
- FR4 material
- Bottom layer dedicated largely as ground plane
- Default track width: 0.3 mm
- Zero DRC violations
- No unrouted nets
- Mounting holes for mechanical integration


# PCB Layout Strategy

## Component Placement
- MCU centrally placed
- Decoupling capacitors positioned close to VDD pins
- Crystal placed near MCU with short traces
- Power regulation section separated from sensitive routing

## Routing Approach
- Clean 45° trace routing
- Short and direct signal paths
- Reduced unnecessary vias
- Organized header alignment
- Controlled trace length for USB lines

## Signal Integrity Considerations
- Solid ground reference plane
- Reduced loop area for high-frequency signals
- Analog and digital domain isolation
- Careful power distribution routing

---

# Design Validation

- Electrical Rule Check (ERC) Passed  
- Design Rule Check (DRC) Passed  
- Zone refill verified  
- No clearance violations  

---

# Knowledge Source & Learning Reference

This project was strongly influenced by concepts learned from the book:

**_Practical Electronics for Inventors_ by Paul Scherz and Simon Monk**

The book was extremely helpful in strengthening the theoretical foundation behind the design decisions used in this board.

## Key Concepts Applied from the Book:

- Power supply filtering and decoupling strategies  
- Proper selection of bulk and ceramic capacitors  
- Ferrite bead usage for analog-digital isolation  
- Crystal oscillator layout practices  
- Pull-up and pull-down resistor design fundamentals  
- Signal integrity basics  
- Grounding and return path understanding  

Instead of placing components mechanically, design decisions were made with an understanding of:

- Why decoupling capacitors must be placed near VDD pins  
- How LDO stability depends on output capacitors  
- Why analog and digital domains should be isolated  
- How trace length impacts clock reliability  

This book significantly improved practical intuition in PCB design and embedded hardware development.

---


# Learning Outcomes

- Professional schematic development workflow  
- 2-layer PCB routing fundamentals  
- Power integrity principles  
- USB interface layout basics  
- Analog and digital separation techniques  
- DRC/ERC validation workflow in KiCad  
- Practical hardware design discipline  

---

# Future Improvements

- Add USB ESD protection IC  
- Replace AMS1117 with switching regulator for better efficiency  
- Add reverse polarity protection  
- Implement impedance-controlled USB routing calculation  
- Add labeled test points for debugging  

---

# Why This Project Matters

This project demonstrates:

- Embedded hardware design capability  
- Understanding of STM32 architecture  
- Practical PCB layout discipline  
- Engineering-driven decision making  
- Structured learning applied to real hardware  

---

# 🧑‍💻 Author

Pranav Duse  
Embedded Systems & PCB Design Enthusiast  
