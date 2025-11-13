# A Theory-Constrained Framework for Data-Driven Learning of Multiple Discrete–Continuous Choices
**Lee, H., Hawkins, J., Kim, D.-K., Bansal, P., & Kim, E.-J. (2025).**  
A theory-constrained framework for data-driven learning of multiple discrete–continuous choices.  
(Under review at *Transportation Research Part B: Methodological*)  
https://ssrn.com/abstract=5606976

---

## Overview
This repository provides an implementation of MDC-LN, a hybrid modeling framework that integrates deep neural networks with theory-constrained lattice networks. The model flexibly learns utility functions underlying multiple discrete–continuous choices while preserving essential theoretical properties.

A gradient-ascent fixed-point iterator predicts the consumption bundle that maximizes the parameterized utility function. The discrepancy between predicted and observed consumption is then backpropagated using implicit-differentiation, enabling stable and efficient training.

---

## Getting Started

### **Dependencies**
- Python 3.10.0
- TensorFlow 2.12.0
- TensorFlow Lattice 2.1.1

---

## Components

### **Dataset**
Due to restrictions on sharing household travel survey data, only **simulated datasets** are included.

- **`Data/generalized_simulation_data`**  
  Simulated data based on the *additively separable* generalized MDCEV utility functions in  
  **Bhat (2008)** – https://doi.org/10.1016/j.trb.2007.06.002  
  (No cross-interaction effects)

- **`Data/emdc_simulation_data`**  
  Simulated data based on the *non-additively separable* eMDC utility functions in  
  **Palma & Hess (2022)** – https://doi.org/10.1016/j.trb.2022.04.005  
  (Includes cross-interaction effects)

---

### **`MDC-LN.ipynb`**
Implements a theory-constrained lattice network assuming **additive separability**:

- Models  
  - **ψ**: individual-specific taste parameters (via deep neural networks)  
  - **γ**: alternative-specific satiation (via lattice networks with concavity + monotonicity constraints)

---

### **`MDC_LN_with_cross_interactions.ipynb`**
Implements the extended MDC-LN framework **without assuming additive separability**, modeling:

- Models
  - **ψ**: individual-specific taste parameters (via deep neural networks)  
  - **γ**: alternative-specific satiation (via lattice networks with concavity + monotonicity constraints)
  - **δ**: cross-alternative interaction effects (via lattice networks with concavity constraints)

---

## Notice
- Detailed explanations of the algorithmic design and theoretical foundations are provided in the full paper.  
- Due to the large number of parameters in the deep learning components, training results may vary across runs.

---

## Authors
- [@Huichang Lee](https://github.com/HuichangLee)

