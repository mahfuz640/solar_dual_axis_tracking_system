# 🌞 Dual Axis Solar Tracker

This project is an **Arduino-based dual axis solar tracker** using **LDR sensors** and **servo motors**.  
It automatically adjusts the solar panel to follow the sun and maximize power generation.

---

## ✨ Features
- 4 LDR sensors to detect sunlight intensity.
- Dual-axis movement (horizontal + vertical).
- Two servo motors for precise tracking.
- Adjustable tolerance for sensitivity.
- Serial Monitor output for debugging.

---

## 🛠️ Hardware Required
- Arduino UNO / Nano / Mega  
- 2 × Servo motors (SG90 / MG995)  
- 4 × LDRs (Light Dependent Resistors)  
- 4 × 10kΩ Resistors  
- Breadboard & jumper wires  
- Solar panel (optional for testing)  

---

## ⚡ Circuit Connections
| Component | Arduino Pin |
|-----------|-------------|
| Servo (Horizontal) | D9 |
| Servo (Vertical)   | D10 |
| LDR Top-Right (TR) | A3 |
| LDR Top-Left (TL)  | A2 |
| LDR Bottom-Right (BR) | A1 |
| LDR Bottom-Left (BL) | A0 |
| Extra Voltage Input (optional) | A6 |

---

## 📂 Code Overview
- Reads **analog values** from LDRs.  
- Calculates **average values** for top, bottom, left, right.  
- Compares values to determine servo adjustments.  
- Moves **vertical servo** (up/down) and **horizontal servo** (left/right).  
- Uses tolerance to reduce unnecessary servo movements.  

---

## ▶️ Usage
1. Build the circuit according to the table above.  
2. Upload the `solar_tracker.ino` sketch to your Arduino.  
3. Open Serial Monitor at **9600 baud** to see sensor + servo values.  
4. Place under sunlight → tracker will auto-align.  

---

## 🔧 Customization
You can adjust sensitivity and servo limits in the code:

```cpp
// Tracking sensitivity
tol = 50; // higher = less sensitive, lower = more sensitive

// Servo limits
int servohLimitHigh = 100;
int servohLimitLow  = 0;
int servovLimitHigh = 100;
int servovLimitLow  = 0;
