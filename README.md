# 3Bit-Synchronous-Counter-7-Segment-Display-Proteus

[cite_start]⚡ 3-Bit Synchronous Counter & Display Systems: A professional-grade hardware design and simulation project centered on sequential logic architectures[cite: 11, 19]. [cite_start]This project covers the complete digital logic lifecycle—from transition layouts and Karnaugh map optimizations to schematic capture, truncation control, and real-time Proteus verification[cite: 11, 23, 148].

🚀 System Overview  
[cite_start]The core of this system is a 3-bit synchronous modulo-8 counter built using industry-standard CD4013 D Flip-Flops[cite: 19, 56]. [cite_start]Driven by a simultaneous clock network to completely eliminate propagation delays and output glitches [cite: 24, 52, 53][cite_start], the binary count is seamlessly intercepted for custom cycle truncation (Modulo-7) [cite: 102, 104] [cite_start]and decoded into a human-readable 7-segment display layout using the CD4511 BCD decoder[cite: 20, 58].

---

## 1. Modulo-8 Synchronous Counter (Base Logic)

### Description
[cite_start]The structural foundation of the project focuses on synchronous sequence tracking[cite: 19, 23]. [cite_start]All flip-flops share a single clock source, driving state transitions in perfect unison[cite: 24, 52]. [cite_start]The circuit configuration relies on precise excitation paths implemented using specialized XOR and AND gates to control how individual bits toggle based on the states of preceding bits[cite: 23, 56]:

* [cite_start]**LSB ($Q_0$):** The output toggles state at every positive clock boundary[cite: 54].
* **Middle Bit ($Q_1$):** Changes state only when the lower-order bit is high[cite: 55].
* **MSB ($Q_2$):** Changes state exclusively when all preceding lower bits are active[cite: 56].

[cite_start]**Symmetrical Orbit:** The counter cycles sequentially through standard binary progression from zero up to seven before automatically rolling back over to zero[cite: 26].

### Simulation Capture
<img width="600" alt="Modulo-8 Counter Schematic" src="assets/modulo8_sim.png" />

---

## 2. BCD Decoder & 7-Segment Display Integration

### Description
[cite_start]To convert raw binary data into intuitive visual readouts, a CD4511 BCD-to-7-Segment Decoder is integrated alongside a common-cathode display[cite: 20, 58, 81]. 

* **Signal Routing:** Counter lines connect to the respective lower-order decoder entry channels[cite: 79].
* [cite_start]**Overflow Protection:** The highest-order entry channel on the decoder is tied permanently to Ground since the maximum count value in a 3-bit system never exceeds seven[cite: 79, 88].
* [cite_start]**Control Flags:** Hardware control lines for lamp testing, blanking, and latch enabling are configured according to the device data sheet specifications to ensure stable, continuous visual presentation[cite: 80].

### Simulation Capture
<img width="600" alt="7-Segment Display Circuit" src="assets/display_sim.png" />

---

## 3. Modulo-7 Truncated Loop Implementation

### Description
[cite_start]A hardware modification designed to compress the natural 8-state sequence into a customized Modulo-7 loop that counts from zero to six and resets immediately without displaying the final state[cite: 102, 122]. 

* [cite_start]**State Interception:** The system monitors the outputs to isolate the specific unwanted state where all three counter bits simultaneously go high[cite: 104, 114].
* **Detection Mechanism:** A logic network acts as a real-time boundary sensor, outputting a clear flag the exact instant this target state attempts to form[cite: 105, 116].
* [cite_start]**Asynchronous Override:** The output of this sensor is routed directly to the asynchronous reset nodes of the D Flip-Flops[cite: 106, 118, 119]. [cite_start]The moment the counter reaches the illegal state, it instantly forces all outputs back to zero, skipping the state entirely and ensuring a clean, glitch-free reset loop[cite: 121, 122].

### Simulation Capture
<img width="600" alt="Modulo-7 Counter Schematic" src="assets/modulo7_sim.png" />

---

## 4. Bonus: 0-to-4 Decimal Counter (JK Flip-Flops)

### Description
[cite_start]An advanced, independent sub-system implementing a 5-state tracking loop using 7476 JK Flip-Flops[cite: 141, 143, 146]. [cite_start]Transition mapping and optimization via Karnaugh maps yield a custom synchronous configuration where each flip-flop input is dynamically driven by combinational logic of the current states[cite: 154, 176, 210]:

* **Flip-Flop 0 ($Q_0$):** Driven by the inverted state of the highest bit to control the baseline toggle rate[cite: 225].
* **Flip-Flop 1 ($Q_1$):** Regulated by combinations of preceding outputs to scale the state changes accurately[cite: 227, 228].
* **Flip-Flop 2 ($Q_2$):** Governed by a feedback loop of the lower bits to trigger the high bit only during appropriate transitions[cite: 229, 230].

[cite_start]An active-low asynchronous override circuit uses a logic gate configuration to catch structural leakage when attempting to enter invalid decimal states, forcing an immediate reset back to zero to guarantee strict containment between states zero and four[cite: 147, 152, 231, 232].

### Simulation Capture
<img width="600" alt="JK Flip-Flop Counter Schematic" src="assets/jk_counter_sim.png" />
