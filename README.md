# Quantum Teleportation of the |1> State

This repository contains an implementation of the **Quantum Teleportation Protocol**, demonstrating the successful transfer of the deterministic quantum state ∣ψ⟩ = ∣1⟩
from **Alice** to **Bob** using the principles of **entanglement** and **conditional classical communication**.

The experiment was implemented using **Qiskit 1.0** and executed on real IBM Quantum hardware via the modern **qiskit-ibm-runtime** service.

---

## Key Experimental Results

The quantum teleportation protocol was executed on a physical backend with high fidelity:

| Metric | Detail |
|--------|--------|
| **Target State** | ∣1⟩ |
| **Execution Backend** | IBM Quantum System (`ibm_fez`) |
| **Total Shots** | 1024 |
| **Successful Outcomes** | 979 |
| **Experimental Fidelity** | ≈ **95.6%** |

The high success rate confirms the viability of the teleportation protocol, with minor deviations attributed to hardware noise sources such as **decoherence** and **measurement error**.

---

## Circuit Flow and Methodology

The teleportation protocol uses a **3-qubit, 3-classical-bit circuit**:

| Qubit | Role |
|--------|------|
| **q₀** | Message qubit — Alice’s state to teleport ($\lvert 1 \rangle$). |
| **q₁** | Entangled qubit — Alice’s half of the Bell pair ($\lvert \Phi^+ \rangle$). |
| **q₂** | Receiver qubit — Bob’s half of the Bell pair |

After generating entanglement and performing Alice’s Bell-basis measurement, the classical bits (**c₀**, **c₁**) are used in **conditional operations** (`if_test`) to apply the required **X** and **Z** corrections to **q₂**, restoring the original ($\lvert 1 \rangle$) state on Bob’s side.

The fully executed circuit and the resulting histogram showing dominant correct outcomes can be viewed in the accompanying notebook.

---

## Setup and Execution

### Prerequisites

Install the required Python libraries:

```bash
pip install qiskit qiskit-aer qiskit-ibm-runtime matplotlib jupyter
