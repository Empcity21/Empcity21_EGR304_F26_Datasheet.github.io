---
title: Bill of Materials
---

# Bill of Materials: Force Sensing Board

**Zice Sun** · Team 103 · Project: **GripRx** · Updated October 30, 2026

## Overview

This page lists every component on my force sensing board schematic, including the parts handed out in class, the parts in my student kit and the parts taken from the Peralta lab stock, plus the debugging hardware (test points, jumpers, the spare GPIO header, the fuse clips and the IC socket). The order quantity follows the course rule: one per instance for the breadboard prototype, one per instance for the PCB, and one or two spares. Parts that can move from the breadboard to the PCB because they sit in a socket or connect by wires (the INA125P, the load cell) are ordered once plus a spare. The table is sorted by vendor, and one purchase request was made for each vendor.

## Budget

| Item | Amount |
| --- | --- |
| Digi-Key parts (11 lines, including spares) | <span>&#36;</span>39.42 |
| Digi-Key shipping (FedEx Ground, cart estimate) | <span>&#36;</span>8.49 |
| Digi-Key tariff (cart estimate) | <span>&#36;</span>4.52 |
| **Total charged to my <span>&#36;</span>60 budget** | **<span>&#36;</span>52.43** |
| Remaining | <span>&#36;</span>7.57 |
| Cost of one board, purchased parts only, no spares (quantity-1 prices) | <span>&#36;</span>26.32 |
| Load cells, Phidgets 3135_0 x 2 (bought out of pocket) | <span>&#36;</span>14.00 plus Phidgets shipping, not charged (course rule) |
| IDC ribbon sockets (bought out of pocket) | <span>&#36;</span>12.00, not charged (course rule) |
| Peralta stock, class-issued parts and kit parts | Not charged (course rule) |

Prices were checked on October 30, 2026 at the linked vendor. The course budget excludes development kits, parts from Peralta, free parts and parts bought out of pocket. Because the purchase request form has lines for tax and shipping, I count them toward my budget, using the Digi-Key cart estimates. A second vendor (Phidgets) would add its own shipping and push the total over <span>&#36;</span>60, so I am buying the two load cells myself; the whole charged order is then a single Digi-Key order. Under the team requirement MF-05 (prototype BOM no more than <span>&#36;</span>150), my board contributes <span>&#36;</span>26.32 in purchased parts.

## Bill of Materials

*Table 1: Bill of materials for the force sensing board, sorted by vendor. Manufacturer part numbers and datasheets are in Table 2.*

| **Part Name/Description** | **Ref Designators** | **Qty/Board** | **Order Qty** | **Unit Cost** | **Total Cost** | **Vendor Link** |
|:--|:--|:--|:--|:--|:--|:--|
| Instrumentation amplifier, DIP-16 | U3 | 1 | 2 | <span>&#36;</span>12.78 | <span>&#36;</span>25.56 | [Digi-Key INA125P-ND](https://www.digikey.com/en/products/detail/texas-instruments/INA125P/254670) |
| TO-220 clip-on heatsink, 24 °C/W | U1 heatsink | 1 | 2 | <span>&#36;</span>0.36 | <span>&#36;</span>0.72 | [Digi-Key HS115-ND](https://www.digikey.com/en/products/detail/boyd-laconia-llc/507302B00000G/5849) |
| Terminal block, 4 positions, 5.08 mm, load cell wires | J4 | 1 | 2 | <span>&#36;</span>1.25 | <span>&#36;</span>2.50 | [Digi-Key ED2637-ND](https://www.digikey.com/en/products/detail/on-shore-technology-inc/OSTTE040161/614586) |
| Shrouded box header, 2 x 4, 2.54 mm, ribbon to UI and motor boards | J1, J2 | 2 | 3 | <span>&#36;</span>1.03 | <span>&#36;</span>3.09 | [Digi-Key 732-5395-ND](https://www.digikey.com/en/products/detail/w%C3%BCrth-elektronik/61200821621/4846916) |
| Jumper shunt, 2.54 mm | JP1, JP2 | 2 | 10 | <span>&#36;</span>0.029 | <span>&#36;</span>0.29 | [Digi-Key S9001-ND](https://www.digikey.com/en/products/detail/sullins-connector-solutions/SPC02SYAN/76375) |
| Schottky diode 40 V 3 A, axial, reverse-polarity protection | D4 | 1 | 3 | <span>&#36;</span>0.71 | <span>&#36;</span>2.13 | [Digi-Key 1801-1N5822CT-ND](https://www.digikey.com/en/products/detail/taiwan-semiconductor-corporation/1N5822/7366597) |
| Ceramic capacitor 0.33 µF 50 V X7R, radial 2.5 mm | C2 | 1 | 3 | <span>&#36;</span>0.35 | <span>&#36;</span>1.05 | [Digi-Key 445-173139-1-ND](https://www.digikey.com/en/products/detail/tdk/FG14X7R1H334KNT06/5802753) |
| Ceramic capacitor 1 µF 25 V X7R, radial 5 mm, RC filter | C8 | 1 | 3 | <span>&#36;</span>0.35 | <span>&#36;</span>1.05 | [Digi-Key 445-173583-1-ND](https://www.digikey.com/en/products/detail/tdk/FG28X7R1E105KRT06/5803197) |
| Resistor 100 Ω 1 % 1/4 W metal film, INA125P gain resistor | R2 | 1 | 10 | <span>&#36;</span>0.042 | <span>&#36;</span>0.42 | [Digi-Key 100XBK-ND](https://www.digikey.com/en/products/detail/yageo/MFR-25FBF52-100R/12795) |
| Resistor 15 kΩ 1 % 1/4 W metal film, RC filter | R5 | 1 | 10 | <span>&#36;</span>0.042 | <span>&#36;</span>0.42 | [Digi-Key 15.0KXBK-ND](https://www.digikey.com/en/products/detail/yageo/MFR-25FBF52-15K/13252) |
| Fuse clip for 5 x 20 mm fuse, PCB mount | F1 holder | 2 | 5 | <span>&#36;</span>0.44 | <span>&#36;</span>2.19 | [Digi-Key F3784-ND](https://www.digikey.com/en/products/detail/littelfuse-inc/01000056Z/2498892) |
| Single-point load cell, 50 kg (CZL635-50) | Off-board via J4 | 1 | 2 | <span>&#36;</span>7.00 | <span>&#36;</span>14.00 out of pocket | [Phidgets 3135_0](https://www.phidgets.com/?prodid=226) |
| IC socket, DIP-16, 7.62 mm | U3 socket | 1 | 3 | — | <span>&#36;</span>0 | Peralta stock, Course list row 79 |
| Ceramic capacitor 0.1 µF 50 V | C3, C5, C6, C11 | 4 | 10 | — | <span>&#36;</span>0 | Peralta stock, Course list row 81 |
| Cartridge fuse 1 A, 5 x 20 mm | F1 | 1 | 4 | — | <span>&#36;</span>0 | Peralta stock, Course list row 85 |
| DC barrel jack, 2.1 x 5.5 mm, PCB | J3 | 1 | 3 | — | <span>&#36;</span>0 | Peralta stock, Course list row 64 (PJ-102AH) |
| Male header strip 1 x 40, 2.54 mm, breakaway | J5, JP1, JP2, TP1–TP7 | 21 pins | 2 | — | <span>&#36;</span>0 | Peralta stock, Course list row 75 |
| Female header strip 1 x 40, 2.54 mm, cut to 1 x 28 | U2 socket | 2 | 3 | — | <span>&#36;</span>0 | Peralta stock, Course list row 76 |
| Resistor 1 kΩ 1/4 W | R1, R10 | 2 | 0 (owned) | — | <span>&#36;</span>0 | Student kit |
| Resistor 330 Ω 1/4 W | R8 | 1 | 0 (owned) | — | <span>&#36;</span>0 | Student kit |
| Resistor 10 kΩ 1/4 W | R9, R11 | 2 | 0 (owned) | — | <span>&#36;</span>0 | Student kit |
| LED, green, power indicator | D1 | 1 | 0 (owned) | — | <span>&#36;</span>0 | Student kit |
| LED, red, debug | D2 | 1 | 0 (owned) | — | <span>&#36;</span>0 | Student kit |
| Tactile pushbutton, debug | SW1 | 1 | 0 (owned) | — | <span>&#36;</span>0 | Student kit |
| PIC18F57Q43 Curiosity Nano | U2 | 1 | 0 (issued) | — | <span>&#36;</span>0 | Issued in class |
| 5 V linear regulator, 1.5 A, TO-220 | U1 | 1 | 0 (issued) | — | <span>&#36;</span>0 | Issued in class |
| 9 V 3 A AC/DC wall adapter | Off-board via J3 | 1 | 0 (issued) | — | <span>&#36;</span>0 | Issued in class |
| IDC ribbon socket, 2 x 4, 2.54 mm (team cables) | Ribbon A and B ends | — | 6 | <span>&#36;</span>2.00 | <span>&#36;</span>12.00 out of pocket | [Digi-Key 732-5444-ND](https://www.digikey.com/en/products/detail/w%C3%BCrth-elektronik/61200823021/4846918) |
| Flat ribbon cable, 8 conductors (team cables) | Ribbon A and B | — | as needed | — | <span>&#36;</span>0 | Lab stock (ask the TA) |
| **Total charged to budget** | | | | | **<span>&#36;</span>52.43** | Digi-Key parts <span>&#36;</span>39.42 + shipping <span>&#36;</span>8.49 + tariff <span>&#36;</span>4.52 |

*Table 2: Manufacturer part numbers and datasheets.*

| **Ref Designators** | **Manufacturer** | **Manufacturer #** | **Datasheet** |
|:--|:--|:--|:--|
| U3 | Texas Instruments | INA125P | [PDF](datasheets/U3_INA125.pdf) |
| U1 heatsink | Boyd | 507302B00000G | [PDF](datasheets/U1_Heatsink_Boyd_507302B00000G.pdf) |
| J4 | On Shore Technology | OSTTE040161 | [PDF](datasheets/J4_OSTTExx0161.pdf) |
| J1, J2 | Würth Elektronik | 61200821621 | [PDF](datasheets/J1_J2_61200821621.pdf) |
| JP1, JP2 | Sullins | SPC02SYAN | [PDF](datasheets/JP_Shunt_SPC02SYAN.pdf) |
| D4 | Taiwan Semiconductor | 1N5822 | [PDF](datasheets/D4_1N5822.pdf) |
| C2 | TDK | FG14X7R1H334KNT06 | [PDF](datasheets/C2_FG14X7R1H334KNT06.pdf) |
| C8 | TDK | FG28X7R1E105KRT06 | [PDF](datasheets/C8_FG28X7R1E105KRT06.pdf) |
| R2 | YAGEO | MFR-25FBF52-100R | [PDF](datasheets/R2_R5_Yageo_MFR.pdf) |
| R5 | YAGEO | MFR-25FBF52-15K | [PDF](datasheets/R2_R5_Yageo_MFR.pdf) |
| F1 holder | Littelfuse | 01000056Z | [PDF](datasheets/F1_Littelfuse_01000056Z.pdf) |
| Off-board via J4 | Phidgets | 3135_0 | [PDF](datasheets/LoadCell_Phidgets_3135_0_Mechanical.pdf) |
| U2 | Microchip | DM164150 | [PDF](datasheets/U2_DM164150_UserGuide.pdf) |
| U1 | STMicroelectronics | L7805ABV-DG | [PDF](datasheets/U1_ST_L78.pdf) |
| Off-board via J3 | BestCH | B09ZTKTLGW | — |
| Ribbon A and B ends | Würth Elektronik | 61200823021 | [PDF](datasheets/IDC_61200823021.pdf) |
| U3 socket | Lab stock (family drawing) | — | [PDF](datasheets/U3_Socket_EDxxDT.pdf) |
| J3 | Lab stock (family drawing) | — | [PDF](datasheets/J3_PJ-102AH.pdf) |
| J5, JP1, JP2, TP1–TP7 | Lab stock (family drawing) | — | [PDF](datasheets/Header_Sullins_PRPC.pdf) |

## Team Ribbon Cables

My board sits in the middle of the daisy chain, so both ribbon cables (Ribbon A to the UI board and Ribbon B to the motor board) plug into my J1 and J2 headers. Each cable needs two Würth 61200823021 IDC sockets ([Digi-Key 732-5444-ND](https://www.digikey.com/en/products/detail/w%C3%BCrth-elektronik/61200823021/4846918), <span>&#36;</span>2.00 each, [datasheet](datasheets/IDC_61200823021.pdf)) and a length of 8-conductor ribbon cable from the lab. I am buying the six sockets for the team (four plus two spares, <span>&#36;</span>12.00) out of pocket, so they are not on a purchase request and do not count toward my <span>&#36;</span>60 budget, as the course rules allow. The ribbon cable itself is not ordered from Digi-Key, because it is sold only as a 300 ft spool.

## Notes on Quantities and Parts


- **U3 (INA125P):** Socketed, so one chip moves from the breadboard to the PCB; 1 spare.
- **U1 heatsink (507302B00000G):** L7805 dissipates about 1.8 W (power budget).
- **J4 (OSTTE040161):** PCB only (load cell wires go straight into the breadboard); 1 spare.
- **J1, J2 (61200821621):** PCB only; jumper wires are used on the breadboard; 1 spare.
- **JP1, JP2 (SPC02SYAN):** Price break at 10 makes 10 cheaper than 6.
- **D4 (1N5822):** Cut tape.
- **C2 (FG14X7R1H334KNT06):** L7805 input capacitor; Digi-Key marks it "not recommended for new design" but in stock; alternate KEMET C320C334K5R5TA.
- **C8 (FG28X7R1E105KRT06):** X7R (not tantalum) so the 10.6 Hz filter is stable; 25 V exceeds the 16 V on the schematic.
- **R2 (MFR-25FBF52-100R):** 1 % sets the gain of 604; 10 cost the same as 4.
- **R5 (MFR-25FBF52-15K):** 10 cost the same as 4.
- **F1 holder (01000056Z):** Two clips hold one fuse; PCB only; price break at 5.
- **Off-board via J4 (3135_0):** Same load cell is used on the breadboard and the PCB; 1 spare. Bought out of pocket because a second vendor adds shipping that would push the order over the budget.
- **U3 socket:** PCB socket and spares.
- **C3, C5, C6, C11:** C5, C6, C11 are 16 V on the schematic; 50 V parts are fine.
- **F1:** Normal (fast-acting) fuse, as the instructor advised.
- **J5, JP1, JP2, TP1–TP7:** J5 10 + JP1/JP2 4 + TP1–TP7 7 = 21 pins per board.
- **U2 socket:** Two 1 x 28 sockets for the Curiosity Nano; one contact is lost at each cut.
- **Kit parts:** the resistors, LEDs and pushbutton come from my student kit. If any value is missing, I will take it from the Peralta drawers instead of ordering it.
- **Peralta stock:** row numbers refer to the course stock planning sheet linked on the assignment page, not to bin locations. Quantities are requests; actual values and lead spacing will be checked before the PCB footprints are assigned.
- **Package size:** every part is through-hole, so the course limit of nothing smaller than 0805 is met, and no part is a breakout module.

## Purchase Requests

| Vendor | Lines | Total | Request |
| --- | --- | --- | --- |
| Digi-Key | 11 | <span>&#36;</span>39.42 + <span>&#36;</span>8.49 shipping + <span>&#36;</span>4.52 tariff = <span>&#36;</span>52.43 | [XLSX](files/Zice_Sun_PR_DigiKey.xlsx) · [PDF](files/Zice_Sun_PR_DigiKey.pdf) · [Digi-Key bulk-upload list](files/Zice_Sun_DigiKey_Bulk_Upload.csv) |
| Peralta stock | 6 | <span>&#36;</span>0 | [XLSX](files/Zice_Sun_PR_Peralta.xlsx) · [PDF](files/Zice_Sun_PR_Peralta.pdf) |

The load cells and the IDC sockets are bought out of pocket, so they have no purchase request. The Digi-Key request has more than 10 lines, so it includes a link to a shared Digi-Key cart made from the bulk-upload list.

## Resources

The full BOM spreadsheet is available [*here*](files/Zice_Sun_BOM.xlsx). Datasheets for the parts are saved in this repository (folder `docs/03-BOM/datasheets`) and linked in Table 2.

## Use of Generative AI

I used Claude (Anthropic) to turn my KiCad schematic into this BOM: listing every reference designator, looking up Digi-Key part numbers, stock and prices, choosing order quantities under the course rule, checking which parts the Peralta stock list covers, filling in the purchase request forms and drafting this page. I checked the part choices against my schematic and component selection page.

Query text:

1. "Does the <span>&#36;</span>60 budget limit include tax?"
2. "What parts does Peralta have that we can use, so they do not have to go on the purchase list?"
3. "Should I buy female headers?" and "The female headers I mean are the ones soldered on the PCB."
4. "So the IDC female connectors are these parts?" (with the team block diagram)
5. "Make the parts my individual datasheet is still missing. Add a link to the team website on the home page."
6. "This is the purchase request form." (with the class purchase request template) and "Read these assignment pages." (Hardware Orders and External Design Review)
7. "I will buy the IDC sockets for both ribbon cables out of pocket. Which datasheets do I still need to download?"
8. "Digi-Key shipping is about <span>&#36;</span>8. Is it included?" and "The form has tax and shipping lines, so they should be included." (I chose to buy the load cells out of pocket.)
