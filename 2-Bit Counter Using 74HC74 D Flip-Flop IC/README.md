# 2-Bit Counter Using 74HC74 D Flip-Flop IC (Pushbutton Clock with Pull-Ups)

This project implements a **2-bit binary ripple counter** on a breadboard using the **74HC74 Dual D-Type Positive Edge-Triggered Flip-Flop IC**.  
The counter increments on each clock pulse from a **pushbutton** and displays the binary count on two LEDs.

---

## 📜 Table of Contents
- [Introduction](#introduction)
- [Components Required](#components-required)
- [7474 Pinout](#7474-pinout)
- [Breadboard Layout](#breadboard-layout)
- [Connections](#connections)
- [Working Principle](#working-principle)
- [Testing](#testing)
- [Troubleshooting](#troubleshooting)

---

## Introduction
A 2-bit counter cycles through the binary sequence `00`, `01`, `10`, `11` (0–3 in decimal) and repeats.  
With the **74HC74 IC** containing two D flip-flops, we can create this counter with minimal wiring.  
This build uses:
- **Pull-up resistors** (10 kΩ) on control lines for stable operation.
- **Pushbutton clock input** for manual counting.

---

## Components Required

| Component                          | Quantity |
|------------------------------------|----------|
| 74HC74 D Flip-Flop IC              | 1        |
| Breadboard                         | 1        |
| Jumper wires                       | As needed|
| LEDs                               | 2        |
| Resistors (330 Ω)                  | 2        |
| Pushbutton (momentary)             | 1        |
| Resistors (10 kΩ pull-ups)         | 5        |
| 3V or 5V DC power source           | 1        |

---

## 7474 Pinout

```

```
  +---+--+---+
```

1CLR|1  +--+ 14|VCC
1D |2       13|2CLR
1CLK|3       12|2D
1PRE|4       11|2CLK
1Q |5       10|2PRE
1Q̄ |6        9|2Q
GND |7        8|2Q̄
+----------+

```

---

## Breadboard Layout

![2-Bit Counter Breadboard](circuit_diagram.jpg)

---

## YouTube Video Link

![2-Bit Counter Breadboard]()

---

## Connections

1. **Insert 74HC74 into breadboard** with notch facing you.
2. **Power:**
   - Pin14 → +V (3V or 5V depending on IC version)  
   - Pin7 → GND
3. **Control Inputs (pull-ups):**
   - Pins 1 (1CLR), 4 (1PRE), 10 (2PRE), 13 (2CLR) → +V **via 10 kΩ resistors**
4. **Flip-Flop Wiring:**
   - Pin2 (1D) ← Pin6 (1Q̄)  
   - Pin12 (2D) ← Pin8 (2Q̄)
5. **Clock Inputs:**
   - Pin3 (1CLK) → Pushbutton → +V  
   - Add 10 kΩ resistor from Pin3 to GND (pull-down)
   - Pin11 (2CLK) ← Pin5 (1Q)
6. **LED Outputs:**
   - Pin5 (1Q) → 330 Ω → LED (LSB) → GND  
   - Pin9 (2Q) → 330 Ω → LED (MSB) → GND

---

## Working Principle
- **FF0 (LSB)** toggles on every rising edge from the pushbutton clock.  
- **FF1 (MSB)** toggles when FF0 output (Q0) goes HIGH to LOW (every second pulse).  
- LEDs display the binary count:
```

Q1 Q0
0  0
0  1
1  0
1  1
(repeats)

```

---

## Testing
1. Power the circuit.
2. Press the pushbutton to increment the count.
3. Observe:
 - **LED0 (Q0)** toggles on each press.
 - **LED1 (Q1)** toggles every two presses.

---

## Troubleshooting
- **No LED change:** Ensure PRE and CLR are pulled HIGH (inactive).
- **Random toggles:** Add a small capacitor (0.1 µF) across pushbutton for debouncing.
- **Always ON/OFF LEDs:** Check Q and Q̄ wiring to D inputs.

---

## Example Output Table

| Press Count | Q1 LED | Q0 LED |
|-------------|--------|--------|
| 0           | OFF    | OFF    |
| 1           | OFF    | ON     |
| 2           | ON     | OFF    |
| 3           | ON     | ON     |
| 4           | OFF    | OFF    |

---

**Author:** Prince Kumar Kushwaha CEO of COSM Electronics
