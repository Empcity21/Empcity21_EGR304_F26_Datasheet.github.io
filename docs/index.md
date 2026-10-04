---
title: Welcome
tags:
- tag1
- tag2
---
<center>
<font size= "6">Zice Sun Datasheet</font><br>
as part of<br>
<font size= "8"> GripRx</font><br>
for<br>
<font size= "5"> Team 103 </font><br>

**Submission: Sep 1st, 2026**
</center>

## Introduction

This datasheet documents my individual contributions to the Team 103 
design project for EGR 304, Fall 2026.

### Project Summary

Team 103 is designing **GripRx**, a prescription-based automatic-resistance grip trainer for hand rehabilitation. The device measures the force a patient applies through a load cell and automatically sets its own mechanical resistance to the level prescribed by a therapist. The system is split into three boards, each built around a PIC18F57Q43 Curiosity Nano: a UI board, a force sensing board, and a motor board, connected in a daisy chain by 8-pin ribbon cables.

### My Contribution

I design the **force sensing board**, the center board of the daisy chain. It measures grip force (load cell, INA125P instrumentation amplifier and active low-pass filter into the ADC), runs the training-session logic, and exchanges messages with the UI board and the motor board.

## Datasheet Pages

- [Block Diagram](01-Block-Diagram/Block-Diagram.md): individual block diagram of the force sensing board
