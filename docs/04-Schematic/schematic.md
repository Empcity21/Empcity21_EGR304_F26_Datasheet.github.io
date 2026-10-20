---
title: Schematic
---

## Overview

This schematic shows the GripRx force sensing board. Sheet 1 contains the 9 V input with a 1 A fuse, reverse-polarity diode and L7805 5 V regulator, the PIC18F57Q43 Curiosity Nano with isolation jumpers, the ribbon connectors to the UI board (J1) and motor board (J2), a spare GPIO header and test points. Sheet 2 contains the load cell amplifier: an INA125P instrumentation amplifier (gain ≈ 748) with a buffered 0.5 V reference, a 9.8 Hz Sallen-Key low-pass filter into ADC RA0, a buffered DAC output to the motor board, and the debug button and LED.

**Note:** GitHub is currently having issues displaying images. If the schematic images below do not display, please download the [schematic PDF](Zice_Schematic.pdf). The schematic PDF is also submitted directly to Canvas.

![Schematic sheet 1: power, microcontroller and connectors](Zice_Schematic_p1.png)

**Figure 1.** Sheet 1: power, microcontroller, connectors and test points.

![Schematic sheet 2: load cell signal chain and debug](Zice_Schematic_p2.png)

**Figure 2.** Sheet 2: load cell signal chain and debug.

## Resources

- [Schematic (PDF)](Zice_Schematic.pdf)
- [KiCad project (ZIP)](Zice_Schematic.zip)

## Use of Generative AI

I used Claude (Anthropic) for this assignment. Claude produced a reference schematic drawing and parts list, fxied the U4A input polarity, a label typo and six missing connections. I did the rest of the wiring, the layout and the section labels myself. Full queries:

1. "I am doing EGR 304 individual assignment schematics, give me the full overview and what to do [assignment link]."

2. "What parts do I need to draw? How do I draw them?"

3. "Generate a sample look of the schematics."

4. "How to draw dashed blocks?"

5. "ERC is good, check my schematics before turning in."