# 🧠 Tiny TPU  
### A Minimal Tensor Processing Unit for Edge AI & Education

<!-- ================= BADGES ================= -->
<p align="center">
  <img src="https://img.shields.io/github/stars/Sam-bot-dev/Tiny-TPU?style=flat-square" />
  <img src="https://img.shields.io/github/forks/Sam-bot-dev/Tiny-TPU?style=flat-square" />
  <img src="https://img.shields.io/github/issues/Sam-bot-dev/Tiny-TPU?style=flat-square" />
  <img src="https://img.shields.io/github/issues-pr/Sam-bot-dev/Tiny-TPU?style=flat-square" />
  <img src="https://img.shields.io/github/license/Sam-bot-dev/Tiny-TPU?style=flat-square" />

</p>

<p align="center">
  <img src="https://img.shields.io/badge/build-experimental-orange?style=flat-square" />
  <img src="https://img.shields.io/badge/Open%20Source-Yes-success?style=flat-square" />
  <img src="https://img.shields.io/badge/Hardware-Verilog-blue?style=flat-square" />
  <img src="https://img.shields.io/badge/AI-Tensor%20Acceleration-purple?style=flat-square" />
</p>

---

## 📌 Overview

**Tiny TPU** is a **lightweight, open-source Tensor Processing Unit (TPU)** built for **learning, experimentation, and research**.

It demonstrates how **AI accelerators** perform tensor operations such as **matrix multiplication** using parallel hardware units — inspired by real-world TPUs but simplified and transparent.

This project is ideal for:
- Students learning computer architecture
- AI + hardware enthusiasts
- Open-source contributors
- Resume-worthy system-level projects

---

## 🚀 Why Tiny TPU?

Big tech companies keep accelerator designs closed.  
**Tiny TPU opens the black box.**

✔ Understand how AI chips work  
✔ Combine ML + hardware knowledge  
✔ Learn systolic & MAC-based designs  
✔ Open-source and beginner-friendly  

---

## ✨ Features

- ⚙️ Matrix Multiply Engine (MAC-based)
- 🧮 Fixed-point arithmetic (8/16-bit)
- 🔄 Parallel processing units
- 🧠 AI-oriented dataflow
- 📦 Modular RTL design
- 🧪 Fully simulation-ready

---

## 🏗 High-Level Architecture

```text
+-------------------+
|   Input Buffer    |
+-------------------+
         |
         v
+-------------------+
| Matrix Multiply   |
| Engine (MACs)     |
+-------------------+
         |
         v
+-------------------+
| Accumulator &     |
| Output Buffer     |
+-------------------+
```

---

## 🛠 Tech Stack

| Layer | Technology |
|-----|------------|
| RTL Design | Verilog / SystemVerilog |
| Simulation | Icarus Verilog |
| Waveform | GTKWave |
| Control | FSM-based |
| Verification | Python (optional) |

---

## 📂 Project Structure

```text
tiny-tpu/
├── rtl/
│ ├── mac_unit.v
│ ├── matrix_engine.v
│ ├── controller.v
│ └── top.v
│
├── testbench/
│ └── tb_top.v
│
├── scripts/
│ └── simulate.sh
│
├── docs/
│ └── architecture.md
│
├── LICENSE
└── README.md
```

---

## 🧪 Getting Started

### Prerequisites
- Icarus Verilog
- GTKWave
- Linux / macOS

### Clone Repository
```bash
git clone https://github.com/Sam-bot-dev/tiny-tpu.git
cd tiny-tpu
```
---

## 📜 License

### Licensed under the MIT License — free to use, modify, and distribute.

## ⭐ Support

### If this project helped you learn something new, give it a star ⭐
### It helps others discover open hardware projects.

## 🔗 Connect With Me

<p align="center">
  <table>
    <tr>
      <td align="center" width="50%">
        <div>
          <img src="https://avatars.githubusercontent.com/Sam-bot-dev?s=120" width="120px;" height="120px;" alt="Bhavesh"/>
        </div>
        <div><strong>Lead Dev</strong></div>
        <div><strong>Bhavesh</strong></div>
        <a href="https://github.com/Sam-bot-dev">🌐 GitHub</a>
      </td>
    </tr>
  </table>
</p>
