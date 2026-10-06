# CAN Communication

## Overview

The system uses the CAN1 controller of the LPC2129 to enable communication between three nodes:

- Main Node
- Fuel Node
- Indicator & Reverse Alert Node

## CAN Configuration

| Parameter | Value |
|---|---|
| CAN Controller | CAN1 |
| CAN Baud Rate | 125 kbps |
| Oscillator Frequency | 12 MHz |
| CPU Clock | 60 MHz |
| Peripheral Clock | 15 MHz |
| CAN RX Pin | P0.25 |
| Frame Type | Standard Data Frame |
| DLC | 4 bytes |

## CAN Message Map

| CAN ID | Source | Destination | Data |
|---:|---|---|---|
| 1 | Fuel Node | Main Node | Fuel percentage |
| 2 | Indicator & Reverse Node | Main Node | Distance in cm |
| 3 | Main Node | Indicator & Reverse Node | Left indicator command |
| 4 | Main Node | Indicator & Reverse Node | Right indicator command |

## Communication Flow

```text
Fuel Node
    |
    | CAN ID 1
    | Fuel %
    v
Main Node
    |
    | CAN ID 3 / 4
    | Indicator commands
    v
Indicator & Reverse Node
    |
    | CAN ID 2
    | Distance
    v
Main Node