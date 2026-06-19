# Constant-gm Biasing of a 4-Transistor OTA Using Negative Feedback

## Overview

This project implements a constant-(g_m) biasing architecture using a compact 4-transistor Operational Transconductance Amplifier (OTA) and a negative-feedback loop. The objective is to reduce the sensitivity of transconductance to temperature variations by automatically adjusting the common-mode bias voltage.

The design was implemented and simulated in **Cadence Virtuoso** using **gpdk180 technology** with a **1.8 V supply**.

---

## Motivation

The transconductance ((g_m)) of MOS transistors changes with temperature and process variations. Since OTA gain and bandwidth are directly related to (g_m), these variations can significantly affect circuit performance.

A constant-(g_m) biasing technique helps maintain a stable transconductance by continuously correcting the bias point through feedback.

---

## Project Objectives

* Design a compact 4-transistor OTA.
* Implement a replica transconductor for transconductance sensing.
* Develop a negative-feedback loop for automatic bias adjustment.
* Analyze transistor operating points.
* Evaluate transconductance stability over temperature.

---

## Architecture

The complete system consists of:

1. **Constant-gm Replica OTA**
2. **Error Amplifier**
3. **Feedback Network**
4. **Main OTA**

### Block Diagram

```text
            +----------------+
            | Reference Current |
            +--------+--------+
                     |
                     v
              +-------------+
              | Error       |
              | Amplifier   |
              +------+------+ 
                     |
                     | Vcm
                     v
      +-----------------------------+
      | Constant-gm Replica OTA     |
      +-------------+---------------+
                    |
                    | Iout = 2gmΔV
                    |
                    v
             Feedback Path
                    |
                    +--------------------+
                                         |
                                         v
                              +----------------+
                              | Main OTA       |
                              +----------------+
```

---

## Constant-gm Principle

The replica OTA generates an output current:


I_{out}=2g_m\Delta V


The feedback loop forces:


I_{out}=I_{ref}


Therefore,


g_m=\frac{I_{ref}}{2\Delta V}


which makes the transconductance primarily dependent on the reference current and reference voltage rather than transistor parameters.

---

## Design Specifications

| Parameter         | Value                         |
| ----------------- | ----------------------------- |
| Technology        | gpdk180                       |
| Supply Voltage    | 1.8 V                         |
| OTA Type          | 4-Transistor OTA              |
| Biasing Method    | Constant-gm Negative Feedback |
| Temperature Range | -20°C to 100°C                |
| Simulation Tool   | Cadence Virtuoso              |

---

## Simulations Performed

* DC Operating Point Analysis
* Temperature Sweep Analysis
* Transconductance Evaluation
* Saturation Region Verification

---

## Key Learnings

* Design of compact OTA architectures.
* Constant-gm biasing techniques.
* Negative-feedback-based bias stabilization.
* Analog circuit simulation using Cadence Virtuoso.
* Operating-point analysis and temperature characterization.

---

## Tools Used

* Cadence Virtuoso
* gpdk180 CMOS Technology
* Analog Design Environment (ADE)

---

## Future Improvements

* Improve temperature stability further.
* Optimize feedback loop gain.
* Reduce transconductance variation across process corners.
* Explore low-power implementations.

---


