# Dome-Aperture-Cavity-Antenna-2.4GHz

Low-cost 2.4 GHz directional cylindrical conducting cavity antenna featuring a passive hemispherical dome-ended aperture for sidelobe suppression and electromagnetic interference (EMI) mitigation in Wireless Sensor Network (WSN) and Internet of Things (IoT) nodes[cite: 1].

---

## Overview

Conventional cylindrical cavity antennas provide an inexpensive way to achieve directional radiation at 2.4 GHz, but abrupt metallic edges at the open aperture cause edge diffraction, azimuthal pattern ripples, and elevated sidelobe levels (SLL)[cite: 1, 2]. Building upon the benchmark flat-aperture cylindrical cavity design by Gautam et al. (2022), this project introduces a **passive conducting hemispherical dome** at the open aperture end[cite: 1, 2].

By smoothing the electromagnetic boundary conditions at the rim, the dome redistributes surface currents and induces a quasi-tapered amplitude and phase distribution across the aperture[cite: 1, 3, 6]. This suppresses edge diffraction and off-axis co-channel interference without requiring multilayer substrates, phased arrays, or complex feed networks[cite: 1, 2, 6].

---

## Key Highlights

* **Sidelobe Level (SLL) Suppression:** Achieves a **4–6 dB** SLL reduction in optimal configurations compared to the flat-aperture reference cavity (e.g., improving SLL from $-11.0\text{ dB}$ to $-15.0\text{ dB}$ at $60^\circ$ HPBW, and reaching $-17.1\text{ dB}$ in parameter sweeps)[cite: 1, 3, 5].
* **Improved Directivity & Front-to-Back ($F/B$) Ratio:** Redirects sidelobe energy into the main lobe, boosting directivity by **0.4–0.9 dB** (up to $10.21\text{ dBi}$) and improving $F/B$ ratio by **3–4 dB** (up to $12.0\text{ dB}$)[cite: 5, 6].
* **Beamwidth & Impedance Stability:** Maintains simulated Half-Power Beamwidth (HPBW) within **$\pm 2^\circ$** of target values ($30^\circ$, $45^\circ$, and $60^\circ$) while preserving impedance matching ($S_{11} < -10\text{ dB}$) around 2.4 GHz[cite: 3, 5, 6].
* **Ultra-Low-Cost Prototyping:** Fabricated for **under $8 per antenna** using folded aluminum sheet, aluminum foil formed over a 3D-printed mold, conductive epoxy, and off-the-shelf ESP-01 / NRF24L01 transceiver modules[cite: 5].

---

## Antenna Geometry & Material Specifications

Both the baseline flat cavity and the proposed dome-ended cavity share identical base dimensions and feeds for direct comparison[cite: 3]:

| Parameter | Specification |
| :--- | :--- |
| **Operating Frequency** | 2.4 GHz[cite: 3] |
| **Cavity Radius ($R$)** | $60\text{ mm}$[cite: 3] |
| **Cavity Length ($L$)** | $300\text{ mm}$[cite: 3] |
| **Wall Thickness ($t$)** | $1\text{ mm}$[cite: 3] |
| **Dome Height ($h_d$)** | $18\text{–}36\text{ mm}$ ($0.3R\text{–}0.6R$, with dome radius $R_d \approx R$)[cite: 3] |
| **Radiator Offset from Base** | $295\text{ mm}$[cite: 3] |
| **Cavity & Dome Material** | Aluminum (PEC)[cite: 3] |
| **Radiator & Substrate** | $35\text{ }\mu\text{m}$ copper trace on FR-4 ($\varepsilon_r = 4.3$, $\tan\delta = 0.02$)[cite: 3] |

---

## Simulation & Experimental Results (2.4 GHz)

### Full-Wave Simulation Framework
All geometries were modeled in **CST Studio Suite 2024** (Frequency-Domain Solver) using $\lambda/25$ fine meshing and 4 adaptive mesh refinement passes[cite: 3]. Dome height ($h_d$), radiator offset, and cavity length ($L$) were co-varied to evaluate $30^\circ$, $45^\circ$, and $60^\circ$ target HPBW regimes[cite: 3].

### Performance Summary

| Configuration | Target HPBW | Simulated HPBW | Directivity | SLL | $F/B$ Ratio | Measured HPBW |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **Reference Flat Cavity** | $60^\circ$[cite: 5] | $60^\circ$[cite: 5] | $9.40\text{ dBi}$[cite: 5] | $-11.0\text{ dB}$[cite: 5] | $8.5\text{ dB}$[cite: 5] | $62^\circ$[cite: 5] |
| **Dome Cavity ($h_d = 0.3R$)** | $60^\circ$[cite: 5] | $59^\circ$[cite: 5] | $9.80\text{ dBi}$[cite: 5] | $-15.0\text{ dB}$[cite: 5] | $11.2\text{ dB}$[cite: 5] | $60^\circ$[cite: 5] |
| **Dome Cavity ($h_d = 0.45R$)** | $45^\circ$[cite: 5] | $45^\circ$[cite: 5] | $10.21\text{ dBi}$[cite: 5] | $-10.2\text{ dB}$[cite: 5] | $10.1\text{ dB}$[cite: 5] | $46^\circ$[cite: 5] |
| **Dome Cavity ($h_d = 0.6R$)** | $30^\circ$[cite: 5] | $31^\circ$[cite: 5] | $10.20\text{ dBi}$[cite: 5] | $-10.9\text{ dB}$[cite: 5] | $12.0\text{ dB}$[cite: 5] | $33^\circ$[cite: 5] |

---

## Hardware Prototyping & Measurement Setup

### Bill of Materials (BOM)
* **Folded Aluminum Sheet (Cavity):** ~$1–2 per unit[cite: 5]
* **3D-Printed Dome Mold (One-Time Tooling):** ~$5–10[cite: 5]
* **Aluminum Foil & Conductive Epoxy/Adhesives:** ~$2[cite: 5]
* **2.4 GHz Transceivers (ESP-01 / NRF24L01):** ~$1.5–3 per module[cite: 5]
* **Total Prototype Cost:** **< $8**[cite: 5]

### RSSI Radiation Measurement Campaign
* **Testbed Geometry:** TX and RX nodes separated by $5\text{ m}$ in both indoor corridor (multipath-present) and open courtyard environments[cite: 3].
* **Angular Sweep Protocol:** Transmitter mounted on a stepper-driven turntable ($1^\circ$ step resolution); RSSI logged every $2^\circ$ and averaged over 3 sweeps per angle to mitigate multipath noise[cite: 3].
* **Measurement Uncertainties:** $\pm 1\text{ dB}$ RSSI quantization and $\pm 0.5^\circ$ angular orientation tolerance[cite: 3].

---

## Practical Design Guidelines & Applications

* **Design Recipe:** Start with $R = 60\text{ mm}$ at 2.4 GHz for $50\text{–}70^\circ$ HPBW; select $h_d \in [0.3R, 0.6R]$ ($0.3R$ for moderate smoothing, $0.6R$ for narrower beams); minimize gaps/seams at the dome-cylinder junction; fine-tune radiator offset in $2\text{–}5\text{ mm}$ increments[cite: 5].
* **WSN & IoT Use Cases:**
  * **Directional MAC & Energy Efficiency:** Reduces unintended wake-ups and off-axis interference, extending sensor node battery life[cite: 5].
  * **RSSI-Based Angular Localization:** Cleaner main-lobe roll-off prevents secondary sidelobe peaks from causing bearing estimation errors[cite: 5].
  * **Interference-Aware Routing:** Enhances spatial reuse and link reliability in dense 2.4 GHz deployments[cite: 1, 5].

---

## Authors & Affiliation

**Abhigyan Patnaik**, Alankar Saxena, Anshu Kashyap, Juttuka Saaketh, Ketan Sahu, Neeraj Gautam, and **Dr. Archana Sharma**  
Department of Electronics and Communication Engineering, IIIT Naya Raipur, Chhattisgarh, India[cite: 1]

---

## Reference

* P. R. Gautam, A. Verma, S. Kumar, D. Prasad, and A. Kumar, *"Design of Directional Antennas for Wireless Sensor Networks and the Internet of Things Experiments,"* IEEE Sensors Letters, vol. 6, no. 9, pp. 1–4, 2022[cite: 7].
