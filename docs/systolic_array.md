# 🧮 Systolic Array Design – Tiny TPU

## 📌 Overview

A **systolic array** is a specialized hardware architecture designed to efficiently perform **matrix multiplication**, which is the core operation in modern AI workloads (neural networks, transformers, CNNs).

In **Tiny TPU**, the systolic array is used to accelerate tensor operations by:
- Exploiting **parallelism**
- Minimizing memory access
- Maximizing data reuse

This document explains the **concept, dataflow, and design approach** used in Tiny TPU.

---

## 🧠 What Is a Systolic Array?

A systolic array is a grid of **Processing Elements (PEs)** where:
- Data flows rhythmically (like a heartbeat — *systole*)
- Each PE performs a small computation
- Partial results propagate across the array

Instead of fetching data repeatedly from memory, data **streams through the hardware**, drastically improving efficiency.

---

## 🔢 Why Systolic Arrays for AI?

Matrix multiplication dominates AI computation:

C = A × B


Systolic arrays are ideal because they:
- Perform **massively parallel MAC operations**
- Reduce memory bandwidth usage
- Are energy-efficient
- Scale naturally with array size

This is why they are used in **TPUs, NPUs, and AI accelerators**.

---

## 🧩 Processing Element (PE)

Each **PE** in Tiny TPU contains:

- One **Multiplier**
- One **Adder**
- One **Accumulator register**
- Input registers for data flow

### PE Operation

acc = acc + (a × b)


Each PE computes **one partial sum per cycle**.

---

## 🏗 Tiny TPU Systolic Array Structure

Tiny TPU uses a **2D systolic array** of PEs.

Example: **4 × 4 array**


- Matrix **A** flows horizontally
- Matrix **B** flows vertically
- Partial sums accumulate inside each PE

---

## 🔄 Dataflow Strategy

Tiny TPU currently targets **Output-Stationary Dataflow**.

### Output-Stationary
- Each PE holds one output element `C[i][j]`
- Inputs `A` and `B` stream through the array
- Accumulator stays local to the PE

### Benefits
✔ Minimal memory access  
✔ Simple control logic  
✔ Easy to scale  

---

## ⏱ Timing & Execution

Matrix multiplication proceeds in **clock cycles**:

1. Cycle 0: Load first elements of A and B
2. Cycle 1–N: MAC operations propagate
3. Final cycle: Output matrix is ready

Latency depends on:
- Matrix size
- Array dimensions
- Clock frequency

---

## 🧪 Example: 2×2 Matrix Multiplication

Given:

A = | a00 a01 |
| a10 a11 |

B = | b00 b01 |
| b10 b11 |


Output:

C00 = a00b00 + a01b10
C01 = a00b01 + a01b11
C10 = a10b00 + a11b10
C11 = a10b01 + a11b11


Each `Cij` is computed by one PE over multiple cycles.

---

## 🛠 RTL Design Plan

### Core Modules

systolic_array/
├── pe.v # Processing Element
├── systolic_array.v # PE grid
├── controller.v # Timing & control FSM
└── top.v # Integration with Tiny TPU


### PE Signals
- `a_in`, `a_out`
- `b_in`, `b_out`
- `acc_out`
- `clk`, `rst`

---

## 📏 Design Parameters

| Parameter | Description |
|--------|-------------|
| ARRAY_SIZE | Number of rows/columns |
| DATA_WIDTH | Bit width (8 / 16) |
| ACC_WIDTH | Accumulator width |
| CLOCK | System clock |

All parameters are **configurable**.

---

## 🚧 Current Status

- [ ] PE RTL implementation
- [ ] 2×2 systolic array
- [ ] Controller FSM
- [ ] Testbench
- [ ] Waveform verification
- [ ] Integration with Tiny TPU core

---

## 🛣 Future Enhancements

- Weight-stationary dataflow
- Pipelined loading
- Quantization support (INT8)
- CNN inference demo
- FPGA synthesis

---

## 🎯 Educational Goal

This systolic array implementation aims to:
- Demystify AI accelerators
- Teach real hardware design concepts
- Bridge ML and computer architecture

---

## 📚 References

- Google TPU architecture (conceptual)
- Hennessy & Patterson – Computer Architecture
- Systolic array research papers

---

## ⭐ Final Note

This is **not a production TPU**.  
It is an **educational, transparent, and extensible accelerator design**.

That is its strength.
