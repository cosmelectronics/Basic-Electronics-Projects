# 4-Bit Counter with 7-Segment Display (74HC74 + CD4511)

This project implements a 4-bit binary counter on a breadboard using **74HC74 Dual D-Type Flip-Flop ICs** and a **CD4511 BCD to 7-Segment Decoder/Driver**.  
The counter increments with a pushbutton clock and displays the count both on LEDs (binary output) and a common-cathode 7-segment display (decimal output).

---

## 📜 Table of Contents
- Introduction  
- Components Required  
- IC Pinouts (74HC74 & CD4511)  
- Breadboard Layout  
- YouTube Video Link  
- Connections  
- Working Principle  
- Testing  
- Troubleshooting  
- Example Output Table  
- Live Demo Link  

---

## 🔎 Introduction
A 4-bit counter cycles through the binary sequence **0000 to 1111** (0–15 in decimal) and repeats.  
This build uses two 74HC74 flip-flop ICs to generate the 4-bit counter, and a CD4511 IC to decode the binary output into decimal for the 7-segment display.  

The project demonstrates:  
- Binary counting with LEDs.  
- Decimal display with 7-segment.  
- Pushbutton clock with pull-up resistors.  

---

## 🧰 Components Required
| Component                  | Quantity | Description |
|----------------------------|----------|-------------|
| Coin Cell 3V Battery       | 2        | Power supply |
| 10 kΩ Resistor             | 9        | Pull-up resistors |
| 220 Ω Resistor             | 11       | Current limiting for LEDs & 7-segment |
| Red LED                    | 4        | Binary count display |
| Pushbutton                 | 1        | Clock input |
| Dual D Flip-Flop (74HC74)  | 2        | Counter implementation |
| Cathode 7-Segment Display  | 1        | Decimal display |
| 7-Segment Decoder (CD4511) | 1        | BCD to 7-segment driver |
| Breadboard + Jumper Wires  | -        | Connections |

---

## 🖇️ IC Pinouts

### 74HC74 D Flip-Flop
```
     +---+--+---+
1CLR |1 +--+ 14| VCC
1D   |2      13| 2CLR
1CLK |3      12| 2D
1PRE |4      11| 2CLK
1Q   |5      10| 2PRE
1Q̄   |6       9| 2Q
GND  |7       8| 2Q̄
    +-----------+
```
---

### CD4511 BCD to 7-Segment Decoder
```
   +---+--+---+
LE |1  +--+ 16| VDD
BĪ |2       15| a
LT̄ |3       14| b
D  |4       13| c
C  |5       12| d
B  |6       11| e
A  |7       10| f
GND|8        9| g
    +---------+
```

---

## 🔌 Breadboard Layout
- Left section: Two 74HC74 ICs wired as a 4-bit counter with LEDs for binary output.  
- Right section: CD4511 connected to 7-segment display for decimal output.  

---

## 🔗 Connections
**Power:**  
- VCC (Pin 14 of 74HC74, Pin 16 of CD4511) → +3V  
- GND (Pin 7 of 74HC74, Pin 8 of CD4511) → Ground  

**74HC74 Flip-Flops:**  
- PRE and CLR pins tied HIGH with 10 kΩ resistors.  
- Q̄ outputs fed back to D inputs for toggling.  
- First FF (Q0) gets clock from pushbutton.  
- Subsequent FFs take clock from previous FF Q output.  

**LEDs:**  
- Q0–Q3 outputs → 220 Ω → LEDs → GND (binary display).  

**CD4511 Decoder:**  
- Inputs A–D connected to Q0–Q3 outputs of counter.  
- Outputs a–g connected to 7-segment via 220 Ω resistors.  
- LT̄, BĪ, LE tied appropriately for normal operation.  

---

## ⚙️ Working Principle
- The pushbutton generates a clock signal.  
- Each press increments the binary count.  
- LEDs show the binary state (Q0–Q3).  
- CD4511 decodes the binary value and drives the 7-segment to show decimal digits **0–9** (repeats after 9).  

---

## 🧪 Testing
1. Power the circuit with 3V from coin cells.  
2. Press the pushbutton → counter increments.  
3. Observe:  
   - LEDs toggle in binary sequence.  
   - 7-segment shows decimal digit.  

---

## 🔧 Troubleshooting
- **No LED/Display change:** Check pull-ups on PRE/CLR.  
- **Unstable counts:** Add 0.1 µF capacitor for pushbutton debouncing.  
- **Incorrect display:** Verify CD4511 pin mapping to 7-segment.  

---

## 📊 Example Output Table
| Press Count | Q3 | Q2 | Q1 | Q0 | Decimal Display |
|-------------|----|----|----|----|-----------------|
| 0 | 0 | 0 | 0 | 0 | 0 |
| 1 | 0 | 0 | 0 | 1 | 1 |
| 2 | 0 | 0 | 1 | 0 | 2 |
| 3 | 0 | 0 | 1 | 1 | 3 |
| 4 | 0 | 1 | 0 | 0 | 4 |
| 5 | 0 | 1 | 0 | 1 | 5 |
| 6 | 0 | 1 | 1 | 0 | 6 |
| 7 | 0 | 1 | 1 | 1 | 7 |
| 8 | 1 | 0 | 0 | 0 | 8 |
| 9 | 1 | 0 | 0 | 1 | 9 |

---

## 🎥 YouTube Video Link
*(Add link here once uploaded)*  

---

## 🌐 Live Demo Link
https://www.tinkercad.com/things/hfiM0nXsM4R-4-bit-counter-using-seven-segment-display  

---

**Author:** Prince Kumar Kushwaha  
**CEO of COSM Electronics**  
