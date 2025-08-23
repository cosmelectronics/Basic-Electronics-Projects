# LED Blink Circuit Using 555 Timer IC (Astable Mode)

This project demonstrates a simple **LED blink circuit** on a breadboard using the **555 Timer IC** in astable mode. The timer generates a continuous on/off signal, making the LED blink automatically.

---

## 📜 Table of Contents
- Introduction  
- Components Required  
- 555 Timer Pinout  
- Breadboard Layout  
- YouTube Video Link  
- Connections  
- Working Principle  
- Testing  
- Troubleshooting  
- Example Output Behavior  
- Live Demo Link  

---

## Introduction
The **555 Timer IC** is one of the most popular integrated circuits used for timing, pulse generation, and oscillation.  
In this project, we configure it in **astable mode**, where the output continuously toggles between HIGH and LOW, causing the LED to blink.  

By changing the capacitor or resistor values, you can adjust the blink speed.  

---

## Components Required
| Component             | Quantity |
|-----------------------|----------|
| 555 Timer IC          | 1 |
| LED                   | 1 |
| Resistor (1 kΩ)       | 1 |
| Resistor (10 kΩ)      | 1 |
| Capacitor (10 µF)     | 1 |
| Breadboard            | 1 |
| Jumper wires          | As needed |
| Power Supply (9V)     | 1 |

---

## 555 Timer Pinout

```
    +---+--+---+
GND  |1       8| VCC
TRG  |2       7| DIS
OUT  |3       6| THR
RESET|4       5| CTRL
    +---+--+---+
```
---

## Breadboard Layout
Below is the actual breadboard circuit for the **LED blink project**:

![LED Blink Circuit](circuit_diagram.png)

---

## YouTube Video Link
LED Blink with 555 Timer Demonstration  

---

## Connections
- **Power:** Pin 8 → +9V, Pin 1 → GND  
- **Output:** Pin 3 → LED → Resistor (330 Ω) → GND  
- **Timing Components:**  
  - Pin 7 → Resistor (10 kΩ) → VCC  
  - Pin 7 → Resistor (1 kΩ) → Pin 6 & Pin 2  
  - Pin 6 & Pin 2 → Capacitor (10 µF) → GND  
- **Control:** Pin 4 → VCC  

---

## Working Principle
- The capacitor charges and discharges through resistors, generating a square wave at the output.  
- The LED connected at the output pin blinks ON and OFF automatically.  
- The blink speed depends on **R1, R2, and C** values.  

**Formula for Time Period (T):**  
T = 0.693 × (R1 + 2R2) × C  

---

## Testing
1. Power the circuit with a 9V battery.  
2. Observe the LED blinking automatically.  
3. Adjust capacitor value to change blinking speed.  

---

## Troubleshooting
- **LED not blinking:** Check capacitor polarity and resistor connections.  
- **LED always ON:** Ensure reset pin (Pin 4) is tied to VCC.  
- **Very fast/slow blink:** Adjust capacitor (10 µF → slower, 1 µF → faster).  

---

## Example Output Behavior
- At power ON → LED starts blinking.  
- ON → OFF → ON → OFF … continuously.  

---

## Live Demo Link
LED Blink Circuit with 555 Timer Demonstration  

---

**Author: Prince Kumar Kushwaha – CEO of COSM Electronics**

