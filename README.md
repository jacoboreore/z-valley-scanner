# 🧭 Valley Scanner — A Numerical Framework to Explore the Riemann Zeta Landscape

**Author:** Jacob Orellana Real

---

## 📘 Overview

**Valley Scanner** is a computational project designed to explore and confirm zeros of the **Riemann Zeta function** through a *homogeneous scanning method* that does **not rely on Gram points, alignment corrections, or interpolation models**.

Instead, the method performs a continuous walk across real numbers converted into the complex domain, identifying *valleys* (local minima) in $|Z(s)|$ that correspond precisely to nontrivial zeros on the critical line $\Re(s)=\frac{1}{2}$.

This project demonstrates a **direct, reproducible pathway to detect zeros**, making the exploration transparent, geometrically intuitive, and free from traditional boundary dependencies.

---

## 🎯 Motivation

Classical approaches to locating zeta zeros often rely on **Gram point alignment** or numerical phase tracking, which introduce discrete artifacts or “gaps” at scale.

The **Valley Scanner** instead follows a continuous, density-preserving process:

* It walks through $t$ values along the critical line, evaluating $|Z(1/2 + it)|$ directly.
* It detects local minima ("valleys") between successive maxima ("mountains").
* Each confirmed valley corresponds to a verified zero of $\zeta(s)$.

This homogeneous structure reproduces the correct zero density naturally, without preconditioning or fitted corrections.
In short: **the terrain itself reveals the zeros.**

---

## 🧩 What’s Published

### 🧠 Research Highlights

* Demonstration that $|Z(s)|$ terrain symmetry can reproduce zero density without Gram alignment.
* Experimental validation at multiple $t$ scales (up to $t \approx 2\times10^{15}$).
* high-$t$ evaluations beyond $t = 10^{20}$ showing numerical stability and precision.
* Complete datasets and Python tools for reproducibility.

### 📄 Academic Paper

The companion paper describes the statistical analysis, comparisons with the Riemann–von Mangoldt prediction, and the datasets used to validate the approach.

> 📘 The paper and datasets together show that a continuous, unaligned scanning process can recover the full zero structure of $\zeta(s)$.

---

## 🧪 Playground: Visualizing Mountains and Valleys

The file **`playground.py`** offers the simplest way to watch the valley scanner in action.
It plots $|Z(s)|$ against $t$ for low-height ranges, showing:

* **Mountains:** local maxima of $|Z(s)|$
* **Valleys:** confirmed zeros of $\zeta(s)$

To run it:

```bash
python3 playground.py
```

You’ll see a graphical plot where each valley corresponds to a confirmed zero.
This script is ideal for newcomers who want to visually confirm how the method detects zeros geometrically.

---

## 📂 Datasets

The repository includes:

* Datasets published in the paper (`refined_sample_*.csv`)
* Additional high-$t$ datasets confirming reproducibility and valley consistency across independent runs.

Each dataset contains:

```
t, absZ, spacing
```

Where:

* **t** = imaginary part along the critical line
* **absZ** = $|Z(s)|$ value
* **spacing** = $\Delta t$ between consecutive zeros

Example dataset link:

> [refined_sample_1122334455.csv](https://github.com/jacoboreore/z-valley-scanner/blob/main/datasets/refined_sample_1122334455.csv)

---

## ⚙️ Technical Notes

* Calculations use **MPFR precision arithmetic** for numerical stability.
* High-$t$ runs are distributed across multi-core EC2 instances (up to 192 CPUs per job).
* Each confirmed zero is verified by symmetric evaluation of conjugate terms.
* The process supports horizontal scaling — distributed batches can theoretically reach *cosmic-$t$* ranges (beyond $10^{22}$) with sufficient resources.

---

## 📈 Reproducibility & Future Work

The project aims to:

1. Provide **open datasets** for peer validation.
2. Encourage **collaboration on large-scale distributed scans**.
3. Refine the theoretical interpretation of valley geometry and zero density.

---

## 💡 Quick Start

Clone the repository:

```bash
git clone https://github.com/jacoboreore/z-valley-scanner.git
cd z-valley-scanner
```

Install dependencies (if required):

```bash
pip install -r requirements.txt
```

Run a quick valley scan visualization:

```bash
python3 playground.py
```

---

## 🛰️ License and Citation

This project is published under the **MIT License**.
If you reference the datasets or visualizations, please cite:

> Orellana, J. *Valley Scanner: A Continuous Method for Detecting Zeta Zeros Without Gram Alignment.* (2025).

---

*“Walk the mountains, rest at the valleys. All is revealed with symmetry.”*
— *Valley Scanner Project, 2025*
