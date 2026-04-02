# 🧠 Revisiting Conservativeness in Fluid Dynamics

## Failure of Non-Conservative PINNs and a Path-Integral Remedy

<p align="center">
  <b>Arun Govind Neelan</b> · Ferdin Sagai Don Bosco · Naveen Sagar Jarugumalli · Suresh Balaji Vedarethinam  
</p>

<p align="center">
  <i>Physics-Informed Deep Learning · Computational Fluid Dynamics · Scientific Machine Learning</i>
</p>

---

## 📄 Paper

📌 Preprint available here: 

---

## 🔥 TL;DR

* ❌ **Non-conservative PINNs fail** for shock-dominated flows
* ⚠️ Artificial viscosity does **not fix shock speed errors**
* 🚨 Stability ≠ physical correctness
* ✅ We introduce **Path-Integral PINNs (PI-PINNs)**
* 🎯 Achieves **correct shock propagation & weak solutions**

---

## 🎯 Problem Statement

Physics-Informed Neural Networks (PINNs) have shown promise for solving PDEs, but their reliability for **hyperbolic systems with discontinuities** remains unclear.

A central question:

> Can PINNs trained on **non-conservative formulations** recover physically correct solutions in the presence of shocks?

---

## ❗ Key Insight

Even though conservative and non-conservative PDEs are **mathematically equivalent**, they are **not numerically equivalent**.

➡️ Non-conservative PINNs:

* Converge to **incorrect weak solutions**
* Produce **wrong shock speeds**
* Remain deceptively **stable**

➡️ Root cause:

* Violation of **Rankine–Hugoniot jump conditions**
* Induced by **non-vanishing residual terms** under viscous regularization 

---

## 💡 Our Contribution

### 1️⃣ Theoretical Diagnosis

* Identify why **non-conservative PINNs fail**
* Connect failure to **weak solution inconsistency**

### 2️⃣ Path-Integral Reformulation

* Based on **Dal Maso–LeFloch–Murat (DLM) theory**
* Introduces **path-consistent loss functions**

### 3️⃣ PI-PINNs (Proposed Method)

* Enforces correct jump conditions
* Works in **primitive-variable formulations**
* Recovers **physically admissible solutions**

### 4️⃣ Extensive Validation

* Burgers’ equation
* Shallow Water Equations
* Sod shock tube (Euler)
* 2D supersonic wedge flow

---

## 🧪 Experimental Suite

| Problem                 | Physics              | Key Challenge          |
| ----------------------- | -------------------- | ---------------------- |
| Burgers’ Equation       | Scalar hyperbolic    | Shock formation        |
| Shallow Water Equations | Balance law + source | Well-balanced property |
| Sod Shock Tube          | Compressible Euler   | Multi-wave interaction |
| Supersonic Wedge        | 2D steady Euler      | Oblique shocks         |

---

## 📊 Main Results

| Method                 | Shock Speed    | Stability   | Physical Accuracy |
| ---------------------- | -------------- | ----------- | ----------------- |
| Non-Conservative PINNs | ❌ Incorrect    | ✅ Stable    | ❌ Wrong           |
| Conservative PINNs     | ✅ Correct      | ⚠️ Moderate | ✅ Good            |
| **PI-PINNs (Ours)**    | 🚀 **Correct** | ✅ Stable    | ✅ **Best**        |

---

## 🧠 Conceptual Takeaway

> **Conservativeness is hierarchical:**

* Mathematical → Numerical → Physical

A method can satisfy PDE residuals yet still violate physics.

---

## 🏗️ Repository Structure

```bash
.
├── burgers/
│   ├── conservative.ipynb
│   └── non_conservative.ipynb
├── swe/
│   ├── conservative.ipynb
│   └── non_conservative.ipynb
├── euler/
│   ├── sod_conservative.ipynb
│   ├── sod_non_conservative.ipynb
│   └── pi_pinn.ipynb
├── wedge/
│   ├── conservative.ipynb
│   └── non_conservative.ipynb
├── requirements.txt
└── README.md
```

---

## ⚙️ Installation

```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
pip install -r requirements.txt
```

---

## 🚀 Quick Start

```bash
jupyter notebook
```

Each notebook includes:

* Problem setup (IC/BC)
* Neural network architecture
* Conservative vs non-conservative loss
* Training loop (Adam + L-BFGS)
* Visualization vs reference solution

---

## 🧩 Method Overview

### Standard PINNs

$$
\mathcal{L} = \mathcal{L}*{PDE} + \mathcal{L}*{IC} + \mathcal{L}_{BC}
$$

---

### PI-PINNs (Ours)

We extend the loss with:

* ✅ Path-integral consistency
* ✅ Shock-aware regularization
* ✅ Weak solution enforcement

---

## 📈 Reproducibility

* All experiments are **fully reproducible**
* Deterministic seeds included
* Reference solutions provided

---

## 📖 Citation

```bibtex

@article{neelan2025physics,
  title={Revisiting Conservativeness in Fluid Dynamics: Failure of Non-Conservative PINNs and a Path-Integral Remedy},
  author={Neelan, Arun Govind and Bosco, Ferdin Sagai Don and Jarugumalli, Naveen Sagar and Vedarethinam, Suresh Balaji},
  journal={arXiv preprint arXiv:2506.22413},
  year={2025}
}
```

---

## 🤝 Contributions

We welcome contributions in:

* Path-conservative neural operators
* Turbulence modeling with PINNs
* Multiphase / Baer–Nunziato systems
* High-dimensional operator learning

---

## 📬 Contact

**Arun Govind Neelan**
📧 [arunneelaniist@gmail.com](mailto:arunneelaniist@gmail.com)

---

## ⭐ Acknowledgment

If this work helps your research:

* ⭐ Star the repo
* 📄 Cite the paper
* 🤝 Share with the community

---

## 🔮 Future Directions

* Physics-informed attention mechanisms
* Hybrid PINN–FVM solvers
* Scalable operator learning (PINO / FNO)


---
