# Automated Circuit Analysis using MATLAB

## Overview
This project implements a **MATLAB-based solver** for DC electrical circuits using **Nodal and Mesh Analysis** techniques.  
It allows users to define circuits with **resistors, voltage sources, and current sources** and automatically calculates **node voltages** and **mesh currents**.

---

## Features
- Handles **resistors, voltage sources, and current sources** in the circuit.
- Supports **nodal analysis** (AV = B) and **mesh analysis** (ZI = V).
- Automatically constructs **coefficient matrices** and **source vectors** from user input.
- Solves equations using **Cramer's Rule** and MATLAB matrix operations.
- Handles different scenarios:
  - Circuits with only voltage sources
  - Circuits with only current sources
  - Mixed-source circuits with/without series resistance

---

## Input Format
The circuit elements are defined in a MATLAB matrix `input`:

| Column | Description |
|--------|-------------|
| 1      | Element Number |
| 2      | From Node / Mesh |
| 3      | To Node / Mesh |
| 4      | Resistance (Ω) |
| 5      | Voltage Source (V) |
| 6      | Current Source (A) |

> **Note:** Node `0` is considered the reference (ground) node.

**Example for Nodal Analysis:**
```matlab
input = [1 0 1 10 100 0;
         2 1 0 20 0   0;
         3 1 2 10 0   0;
         4 2 0 20 0   0;
         5 0 2 0  0   2];
