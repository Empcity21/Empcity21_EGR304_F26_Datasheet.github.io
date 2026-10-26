---
title: Block Diagram
hide:
  - navigation
  - toc
---

# Block Diagram: Force Sensing Board

**Zice Sun** · Team 103 (Duotao Gao, Gabriel Toneser Facchin, Zice Sun) · Project: **GripRx**, a prescription-based automatic-resistance grip trainer

## Overview

This page shows the hardware layout of my subsystem, the force sensing board, and how it connects to my teammates' boards. The block diagram is the starting point for component selection and the schematic: it fixes which microcontroller peripherals and pins I use, which signals cross the ribbon cables, and which power rail each part runs on.

- **Role in the system.** The force sensing board sits in the middle of the team's daisy chain. It measures grip force, runs the training-session logic, and talks to the UI board (Duotao Gao) on ribbon connector J1 and to the motor board (Gabriel Toneser Facchin) on ribbon connector J2.
- **Sensor.** A Phidgets 3135_0 50 kg load cell (Wheatstone bridge) produces a millivolt-level differential signal. It is amplified by a Texas Instruments INA125P instrumentation amplifier (gain 604, using its internal 1.24 V reference) and smoothed by a passive RC low-pass filter (15 kΩ, 1 µF, cutoff about 10.6 Hz) before it reaches the ADC on pin RA0. Each signal-conditioning stage is a separate block. Following instructor feedback, the earlier MCP6004 active filter and op-amp buffers were removed to keep the circuit simple.
- **Debug.** A debug LED on RD2 and a debug button on RD3 (10 kΩ pull-up with RC debounce) let the firmware be tested without the other boards.
- **Outputs to teammates.** The board has no actuator of its own. It sends a FORCE_OK safety line (digital output RD1) and an analog copy of the force (FORCE_ANA, DAC output RA2) to the motor board, and exchanges UART messages with both boards.
- **Power.** A 9 V, 3 A wall adapter (BestCH, issued in class) feeds an STMicroelectronics L7805ABV-DG linear regulator, which supplies a regulated 5 V rail to every part on the board. No power is passed over the ribbon cables; pin 8 of each ribbon only shares ground.

## Block Diagram

![Block diagram of the force sensing board: load cell, INA125P instrumentation amplifier and passive RC low-pass filter feeding the ADC of a PIC18F57Q43 Curiosity Nano, with UART, digital and DAC connections to ribbon connectors J1 and J2, inside a 5 V regulated region supplied from a 9 V wall adapter](block-diagram.png)

**Figure 1.** Individual block diagram of the force sensing board, updated after instructor feedback. Arrows show signal direction; every part has its manufacturer and part number.

The editable source of Figure 1 is available as a [draw.io file](block-diagram.drawio), and the source and image together as a [zip archive](block-diagram-source.zip).

## Microcontroller Peripherals and Pins

**Table 1.** PIC18F57Q43 Curiosity Nano peripherals used on the force sensing board.

| Peripheral | Type | Pin | Signal | Direction | Connects to |
|---|---|---|---|---|---|
| ADC | ADC | RA0 | Filtered load-cell voltage | In | RC low-pass filter output |
| DAC1 | DAC | RA2 | FORCE_ANA | Out | J2 pin 6 → motor board |
| Digital output | DO | RD1 | FORCE_OK | Out | J2 pin 3 → motor board |
| Digital output | DO | RD2 | Debug LED | Out | Red LED + 1 kΩ to GND |
| Digital input | DI | RD3 | Debug button | In | Tactile switch, 10 kΩ pull-up, RC debounce |
| Digital input | DI | RD0 | UI_RUN | In | J1 pin 3 ← UI board |
| UART1 | UART | RC2 (TX) | UART F→U | Out | J1 pin 1 → UI board |
| UART1 | UART | RC3 (RX) | UART U→F | In | J1 pin 2 ← UI board |
| UART3 | UART | RA3 (TX) | UART F→M | Out | J2 pin 1 → motor board |
| UART3 | UART | RA4 (RX) | UART M→F | In | J2 pin 2 ← motor board |

The UART pins use the default UART1 (RC2/RC3) and UART3 (RA3/RA4) locations, which keeps the debugger pins RB6/RB7 and the USB serial pins RF0/RF1 free.

## Ribbon Cable Connectors

Both connectors follow the class standard (pins 1–5 digital, pins 6–7 analog, pin 8 ground) and match the team block diagram.

**Table 2.** Connector J1: force sensing board to UI board.

| Pin | Type | Signal | Direction | My pin |
|---|---|---|---|---|
| 1 | Digital | UART F→U | Force → UI | RC2 (U1TX) |
| 2 | Digital | UART U→F | UI → Force | RC3 (U1RX) |
| 3 | Digital | UI_RUN | UI → Force | RD0 (DI) |
| 4–5 | Digital | Not connected | — | — |
| 6–7 | Analog | Not connected | — | — |
| 8 | Ground | Common ground | — | GND |

**Table 3.** Connector J2: force sensing board to motor board.

| Pin | Type | Signal | Direction | My pin |
|---|---|---|---|---|
| 1 | Digital | UART F→M | Force → Motor | RA3 (U3TX) |
| 2 | Digital | UART M→F | Motor → Force | RA4 (U3RX) |
| 3 | Digital | FORCE_OK | Force → Motor | RD1 (DO) |
| 4–5 | Digital | Not connected | — | — |
| 6 | Analog | FORCE_ANA | Force → Motor | RA2 (DAC1) |
| 7 | Analog | Not connected | — | — |
| 8 | Ground | Common ground | — | GND |

## Power Supplies

**Table 4.** Power rails on the force sensing board.

| Rail | Source | Regulated | Max current | Powers |
|---|---|---|---|---|
| +9 V DC | BestCH 9 V 3 A wall adapter (issued in class) | No | 3 A | L7805ABV-DG regulator input |
| +5 V DC | STMicroelectronics L7805ABV-DG linear regulator | Yes | 1.5 A | Curiosity Nano, INA125P, load cell excitation |

## Open Items

- The instructor approved the INA125P and advised removing the op-amp filter and buffers; the diagram, component selection, schematic and power budget now reflect that.
- The 9 V adapter is the class-issued BestCH 9 V 3 A unit (no manufacturer part number); its polarity and plug size will be measured before the board is first powered.
- The schematic powers the Curiosity Nano from the 5 V rail through jumper JP1 (JP2 disables its on-board regulator); set its target voltage to 5.0 V so that its I/O levels match the 0–5 V ribbon signals.

## Use of Generative AI

Generative AI (Claude) was used to summarize the assignment requirements, draft the layout of the draw.io block diagram from the team block diagram and the course template, and draft the text and tables on this page. I reviewed and edited the diagram, the pin assignments and the text before submission.

Query text:

1. I am doing the individual assignment, give me detailed instructions and explanation on each part. [link to the Individual -- Block Diagram assignment]
