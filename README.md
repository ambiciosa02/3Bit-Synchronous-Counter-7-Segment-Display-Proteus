# 🔢  Synchronous Counter with D Flip-Flops and 7-Segment Display (Proteus)

## 📌 Project Title
**Realization of a Synchronous Counter using D Flip-Flops with 7-Segment Display under Proteus**

## 🎯 1. Project Objective
The main objective of this practical work (TP2) is to **design**, **simulate**, and **verify** a **3-bit synchronous counter** using **D flip-flops**, and to display the counting values on a **7-segment display** via a **CD4511 BCD-to-7-segment decoder**.

---

## 🧱 2. Project Structure

The project is divided into four main parts:

### 🔷 Part A – Modulo-8 Synchronous Counter
- ✅ Design a 3-bit synchronous counter using D flip-flops (type 4013).
- ✅ Use logic gates (XOR, AND) to implement the following excitation equations:
  - `D0 = ~Q0`
  - `D1 = Q1 ⊕ Q0`
  - `D2 = Q2 ⊕ (Q1 · Q0)`
- ✅ Connect all flip-flops to the same clock signal.
- ✅ Visualize outputs `Q2, Q1, Q0` using LogicProbes.
- ✅ Verify counting sequence:  
  `000 → 001 → 010 → 011 → 100 → 101 → 110 → 111 → 000`

### 🔷 Part B – Adding 7-Segment Display
- ✅ Add **CD4511** decoder and **7SEG-COM-CATHODE** display.
- ✅ Connect counter outputs:
  - `Q0 → A`, `Q1 → B`, `Q2 → C`, `D → GND`
- ✅ Configure `LT`, `BI`, and `LE` pins for normal operation.
- ✅ Verify display shows: `0, 1, 2, 3, 4, 5, 6, 7`

### 🔷 Part C – Modifying Counter (0 to 6)
- ✅ Remove the unwanted state `111` (7).
- ✅ Detect state `111` using a **3-input AND gate**.
- ✅ Connect the reset signal to the **CLR** pins of all D flip-flops (asynchronous reset).
- 🔄 New cycle: `0 → 1 → 2 → 3 → 4 → 5 → 6 → 0`

### ⭐ Part D – Bonus: JK Flip-Flop Counter (0 to 4)
- ✅ Design a decimal counter (0 to 4) using **JK flip-flops (7476)**.
- ✅ Implement asynchronous reset when state `101` (5) is detected.
- ✅ Use Karnaugh maps to derive logic equations for `J` and `K` inputs.
- ✅ Display results on 7-segment display via CD4511.

---

## 🧰 3. Components Used (Proteus)
| Component | Reference |
|-----------|-----------|
| D Flip-Flop | 4013 |
| JK Flip-Flop | 7476 |
| Logic gates | XOR, AND, NAND |
| BCD Decoder | CD4511 |
| Display | 7SEG-COM-CATHODE |
| Probes | Logic probes / oscilloscope |

---

## 📚 4. Key Concepts Covered
- 🕰️ Synchronous vs asynchronous counters
- 📊 Excitation tables and logic equations
- 🔍 State detection and reset logic
- 🔢 BCD decoding and 7-segment display driving
- 🗺️ Karnaugh map simplification
- 💻 Proteus simulation and debugging

---

## 🖥️ 5. Simulation Results
- ✅ All counting sequences were verified via simulation.
- ✅ 7-segment display correctly shows each count.
- ✅ Asynchronous reset successfully removes unwanted states.

---

## 🚀 6. How to Run the Simulation
1. 📂 Open the `.pdsprj` Proteus project file.
2. 🔌 Ensure all components are correctly wired as per the schematic.
3. ▶️ Run the simulation and observe:
   - 🔵 Logic probes for binary output.
   - 🟢 7-segment display for decimal readout.
4. ⏰ Use the clock source to trigger counting.

---

## 📁 7. Files Included
| File | Description |
|------|-------------|
| `TP2_RACHDI_KAOUTAR.pdf` | 📄 Full TP report (French) |
| `README.md` | 📖 This file |
| `schematic_partA.pdsprj` | 🔷 Modulo-8 counter |
| `schematic_partB.pdsprj` | 🔷 With 7-segment display |
| `schematic_partC.pdsprj` | 🔷 Counter 0→6 |
| `schematic_partD.pdsprj` | ⭐ JK counter 0→4 (bonus) |
| `screenshots/` | 📸 Simulation captures |

---

## 📧 8. Author Contact
For any questions or collaboration:  
**Kaoutar Rachdi** – [Your email or contact info]

---

## 🙏 9. Acknowledgments
Special thanks to **Pr. Abdelilah ET-TALEBY** for supervision and guidance.

---

## ⚖️ 10. License
📚 This project is for **educational purposes only**.
