# ⏰ Digital Clock Logic System Design

🎓 **Institution:**Capital University, Faculty of Engineering  

Welcome to the Digital Clock Logic System! This project is a purely hardware-based digital clock featuring real-time tracking and an integrated alarm system. It is built entirely using discrete logic ICs, counters, and timers, demonstrating fundamental digital electronics principles.

## ✨ Key Features

*   **⏲️ Precise Timing:** Utilizes a 555 Timer IC configured in astable mode to generate a highly accurate 1 Hz square wave heartbeat.
*   **🔢 Direct Display Drive:** Employs CD4026 decade counters to seamlessly track time and directly drive the 7-segment displays.
*   **🔄 Smart Rollover Logic:** Integrates asynchronous reset mechanisms via AND gates to ensure accurate rollovers (seconds and minutes reset at 60, hours reset at 24).
*   **🚨 Hardware Alarm System:** Features a reliable alarm using a 74LS85 4-bit magnitude comparator.
*   **🎛️ Manual Presets:** Allows users to set the target alarm time manually using DIP switches.
*   **🔊 Audio-Visual Alerts:** When the comparator detects a match between the current time and the preset time, it outputs a HIGH signal to trigger a buzzer and flash the displays.

## 🧰 Hardware Components

*   **555 Timer IC:** For the 1 Hz clock pulse.
*   **CD4026 ICs:** Decade counters with 7-segment display drivers.
*   **7-Segment Displays:** For visual time output.
*   **Discrete AND Gates:** Used for asynchronous resetting.
*   **74LS85 4-bit Magnitude Comparator:** For alarm matching logic.
*   **DIP Switches:** For inputting the binary/BCD alarm preset.
*   **Buzzer:** For the audible alarm.

## 🧠 System Architecture

### 1. Clock Generation
The system's foundational pulse is created by the 555 timer. Resistor and capacitor values are carefully selected in the astable configuration to produce exactly one pulse per second (1 Hz).

### 2. Time Counting
The 1 Hz pulse feeds into the first CD4026 counter (Seconds - Units). As it counts from 0 to 9, it carries over to the next counter (Seconds - Tens). This cascading logic continues through the Minutes and Hours stages.

### 3. Asynchronous Resets
Standard counters count upwards, but time requires specific cutoffs. AND gates monitor the binary outputs of the counters. 
*   When the *Seconds* or *Minutes* reach 60, the AND gate triggers the reset pins.
*   When the *Hours* reach 24, a similar AND gate configuration resets the system to 00:00:00.

### 4. Alarm Logic
The 74LS85 comparator constantly compares the current BCD state of the clock with the state defined by the user via DIP switches. Once the A=B condition is met, the HIGH output activates the buzzer circuit and flasher.

---
*Designed for reliable hardware operation, showcasing the power of discrete digital logic!* 🚀
