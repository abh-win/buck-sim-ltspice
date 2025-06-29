 # Buck Converter Simulation and Ripple-Efficiency Optimization (LTspice)

This project simulates a 12V-to-5V DC-DC buck converter using LTspice, analyzing how varying inductance values affect output voltage ripple and power conversion efficiency.

---

## ⚙️ Project Overview

- **Tool Used**: LTspice 24.1.9 (Windows)
- **Topology**: Buck Converter (12V input → 5V output)
- **Switching Control**: PWM with 43% duty cycle (`PULSE` source)
- **Load**: 6 Ω resistor
- **Capacitor**: 47 µF (fixed)
- **Inductor Sweep**: 22 µH → 470 µH using `.step`

---

## 📊 Parametric Analysis (Inductor Sweep)

Measured from **5 ms to 10 ms** to focus on steady-state behavior.

| Step | L (µH) | V<sub>max</sub> (V) | V<sub>min</sub> (V) | Ripple (mV) | P<sub>out</sub> (W) | P<sub>in</sub> (W) | Efficiency (%) |
|------|--------|----------------------|----------------------|--------------|---------------------|---------------------|----------------|
| 1    | 22     | 4.9837               | 4.9659               | 17.72        | 4.1254              | 4.3444              | 94.96          |
| 2    | 47     | 4.9875               | 4.9790               | 8.45         | 4.1392              | 4.3552              | 95.04          |
| 3    | 100    | 4.9943               | 4.9878               | 6.53         | 4.1518              | 4.3675              | 95.06          |
| 4    | 220    | 5.0049               | 4.9905               | 14.40        | 4.1608              | 4.3765              | 95.07          |
| 5    | 470    | 5.0278               | 4.9775               | 50.37        | 4.1636              | 4.3768              | 95.13          |

---

## 📈 Key Observations

- Ripple decreased from 22 µH to 100 µH, reaching a **minimum of ~6.5 mV**
- Efficiency remained **stable around 95%**, peaking at **470 µH**
- **Ripple increased sharply** at 470 µH due to underdamped LC behavior
- Demonstrated that **larger inductors don’t always reduce ripple**, highlighting real-world design trade-offs

---

## 📂 Files Included

| File Name               | Description                                                          |
|-------------------------|----------------------------------------------------------------------|
| `buck_coverter.asc`     | LTspice schematic of the buck converter circuit                      |
| `buck_coverter.txt`     | LTspice database file (auto-generated; stores simulation state)      |
| `buck_coverter.plt`     | Plot settings file for saved waveform views (optional)               |
| `buck_coverter.raw`     | Raw waveform output data for LTspice plots                           |
| `buck_coverter.log`     | Simulation output log containing `.measure` results                  |
| `result_log.txt`        | Cleaned results table (efficiency, ripple, power) for easy reference |

---

📌 *Created as a self-initiated ECE project to demonstrate power electronics modeling, simulation automation, and design insight.*
## Author
## Abhinav Jha
