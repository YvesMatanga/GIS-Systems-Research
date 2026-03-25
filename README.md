# 🚦 Optimal Transport Network Design using Bilevel Programming

## 📌 Overview
This repository implements a **Transport Network Design Problem (TNDP)** using a **bilevel programming framework**. The goal is to optimise road network expansion decisions while accounting for realistic user behaviour in traffic assignment.

The framework captures:
- **Planner decisions** (which roads to build)
- **User behaviour** (route choices under congestion)

A real-world **case study of Kinshasa** demonstrates the effectiveness of the approach.

---

## 🧠 Problem Description

### Upper-Level Problem (ULP)
The planner determines which candidate roads to construct under a budget constraint.

- Decision variables: Binary (build / not build)
- Objective: Minimise total travel time in the network

---

### Lower-Level Problem (LLP)
Given a network configuration, traffic flows are assigned according to **User Equilibrium (Wardrop’s First Principle)**:

> No traveller can reduce their travel time by changing routes unilaterally.

---

t_ij(x) = t0_ij * (1 + α * (x_ij / C_ij)^4)


Where:
- `t0_ij`: free-flow travel time  
- `x_ij`: traffic flow  
- `C_ij`: capacity  
- `α`: congestion parameter  

---

## ⚙️ Methodology

| Component | Description |
|----------|------------|
| Network Model | Graph-based (NetworkX) |
| Traffic Assignment | User Equilibrium formulation |
| Objective Function | Integral of travel time |
| Optimisation | Metaheuristic bilevel search |

---

## 🚀 Algorithms Implemented

- Greedy-Seeded Simulated Annealing (Gr-SA)
- Greedy Tabu Search (GrA-TS)
- Genetic Algorithm (GA)
- Particle Swarm Optimisation (PSO)
- Ant Colony Optimisation (ACO)

---

## 📊 Key Results

- ~30% reduction in total travel time  
- Significant reduction in congestion (V/C > 1)  
- High solution stability across runs  
- Improved network efficiency  

---

## 🧪 Sensitivity Analysis

The model is evaluated under varying conditions:

- Demand scaling (0.6× – 2.0×)
- Capacity variation (±20%)
- Budget variation (±30%)
- BPR parameter variations

---

## 🏙️ Case Study: Kinshasa

- Realistic road network modelling  
- OD demand estimated from transport studies  
- Validation using:
  - Volume-to-capacity ratios
  - Flow distributions
  - Network structure metrics  

---

## 🧩 Repository Structure

---

## 🛠️ Technologies

- Python  
- Pyomo  
- NetworkX  
- NumPy / SciPy  
- Matplotlib  

---

## ▶️ Usage

### Clone repository
```bash
git clone https://github.com/yourusername/TNDP-bilevel.git
cd TNDP-bilevel
