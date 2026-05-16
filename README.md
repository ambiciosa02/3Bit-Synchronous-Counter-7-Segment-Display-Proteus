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

  <img width="477" height="253" alt="image" src="https://github.com/user-attachments/assets/91d1809f-c6df-4b99-b6d1-ced453aae5c4" />


### 🔷 Part B – Adding 7-Segment Display
- ✅ Add **CD4511** decoder and **7SEG-COM-CATHODE** display.
- ✅ Connect counter outputs:
  - `Q0 → A`, `Q1 → B`, `Q2 → C`, `D → GND`
- ✅ Configure `LT`, `BI`, and `LE` pins for normal operation.
- ✅ Verify display shows: `0, 1, 2, 3, 4, 5, 6, 7`

  <img width="418" height="351" alt="image" src="https://github.com/user-attachments/assets/cf952003-908b-4197-ad94-71ce55613d0b" />


### 🔷 Part C – Modifying Counter (0 to 6)
- ✅ Remove the unwanted state `111` (7).
- ✅ Detect state `111` using a **3-input AND gate**.
- ✅ Connect the reset signal to the **CLR** pins of all D flip-flops (asynchronous reset).
- 🔄 New cycle: `0 → 1 → 2 → 3 → 4 → 5 → 6 → 0`


<img width="367" height="278" alt="image" src="https://github.com/user-attachments/assets/051d4a3c-a58b-4c20-8b7b-bbd1e14bfb0a" />



### ⭐ Part D – Bonus: JK Flip-Flop Counter (0 to 4)
- ✅ Design a decimal counter (0 to 4) using **JK flip-flops (7476)**.
- ✅ Implement asynchronous reset when state `101` (5) is detected.
- ✅ Use Karnaugh maps to derive logic equations for `J` and `K` inputs.
- ✅ Display results on 7-segment display via CD4511.

<img width="377" height="350" alt="image" src="https://github.com/user-attachments/assets/ddaab85f-8b24-4a39-94d8-e04399e74ec2" />



## 🧰 3. Components Used (Proteus)
| Component | Reference |
|-----------|-----------|
| D Flip-Flop | 4013 |
| JK Flip-Flop | 7476 |
| Logic gates | XOR, AND, NAND |
| BCD Decoder | CD4511 |
| Display | 7SEG-COM-CATHODE |


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



## 🙏 9. Acknowledgments
Special thanks to **Pr. Abdelilah ET-TALEBY** for supervision and guidance.



## ⚖️ 10. License
📚 This project is for **educational purposes only**.
