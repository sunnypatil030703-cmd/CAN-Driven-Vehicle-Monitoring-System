# Hardware Configuration

## Microcontroller

- Microcontroller: LPC2129
- Architecture: ARM7TDMI
- CAN Controller: CAN1
- CAN Communication Speed: 125 kbps
- Crystal Frequency: 12 MHz
- CPU Clock: 60 MHz
- Peripheral Clock: 15 MHz

---

## CAN Interface

| LPC2129 Pin | Function |
|---|---|
| P0.25 | CAN1 RX |

The CAN1 transmit/receive interface is configured through the LPC2129 pin function selection registers.

---

## Main Node

The Main Node is responsible for:

- Vehicle mode selection
- Left indicator control
- Right indicator control
- Fuel percentage reception
- Engine temperature measurement
- LCD display
- Reverse-distance monitoring

### External Interrupts

| Pin | Interrupt | Function |
|---|---|---|
| P0.1 | EINT0 | Forward / Reverse mode |
| P0.3 | EINT1 | Left indicator |
| P0.7 | EINT2 | Right indicator |

### LCD

| Pin | Function |
|---|---|
| P0.8–P0.15 | LCD 8-bit data bus |
| P0.16 | LCD RS |
| P0.17 | LCD EN |
| P0.18 | LCD RW |

---

## Fuel Node

The Fuel Node measures the analog fuel-level signal using the LPC2129 ADC.

### ADC Configuration

| Parameter | Value |
|---|---|
| ADC Channel | Channel 0 |
| ADC Resolution | 10-bit |
| Reference Voltage | 3.3 V |

The ADC value is converted to voltage using:

```text
Voltage = (ADC_Value × 3.3) / 1023