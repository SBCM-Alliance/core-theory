# Mathematical Specification for SBCM (v2.0)
**General Theory of Administrative Hydraulics and Entropic Elasticity**

**Version:** 2.0  
**Author:** Hokuto Koyama (SBCM Alliance, github:Melnus)  
**References:** SBCM Core Theory, Notes #6-#8, Case Studies 001-002

---

## 1. Fundamental Units & Potential Capacity

SBCM redefines the municipality not as a mere administrative label, but as a physical **"Field Unit (Block)"** with a finite capacity to retain energy (wealth).

### 1.1 The Standard Block ($B_{std}$)
The fundamental quantum of governance structure.

$$
B_{std} = \frac{P_{total}}{N_{muni}} \approx 72,176 \quad [\text{persons}]
$$

### 1.2 Potential Entropic Capacity ($C_{pot}$) [Ref: Note #7]
The limit volume of complexity (wealth, information, infrastructure) that a single block can physically maintain.

$$
C_{pot} = \alpha \cdot P_{density} \cdot M_{mesh}
$$

*   $P_{density}$: Population Density (Basic interaction potential).
*   $M_{mesh}$: Mesh Connectivity Coefficient (Local Multiplier/LM3). Higher internal circulation increases the capacity to trap entropy.
*   $\alpha$: Dimensional adjustment constant.

---

## 2. Field Theory & The Continuity Equation [Ref: Part 4]

Regional economy is described not as discrete points, but as a continuous **"Fluid Field of Wealth."**

### 2.1 The SBCM Governing Equation
The time evolution of Economic Density $\rho$ at coordinate $\mathbf{x}$ follows the Equation of Continuity:

$$
\frac{\partial \rho}{\partial t} + \nabla \cdot \mathbf{J} = \sigma - \delta(\rho)
$$

*   $\rho(\mathbf{x}, t)$: **Economic Density** (Accumulated Wealth/Stock).
*   $\mathbf{J}(\mathbf{x}, t) = \rho \mathbf{v}$: **Economic Flux Vector** (Flow of Wealth).
*   $\nabla \cdot \mathbf{J}$: **Divergence**. The rate of inflow/outflow.
    *   $\nabla \cdot \mathbf{J} > 0$: **Leakage/Extraction** (The Straw Effect).
    *   $\nabla \cdot \mathbf{J} < 0$: **Retention/Accumulation** (Gravity Well).
*   $\sigma$: **Source Term** (Value Creation via Labor/Energy).
*   $\delta(\rho)$: **Sink Term** (Dissipation via Maintenance Costs/Entropy).

### 2.2 Vector Definition of the "Straw Effect"
The Straw Effect is defined as a state where flux vectors align towards a central high-gravity point (e.g., Tokyo), maximizing positive divergence in local regions.

$$
\text{Straw Effect} \iff \forall \mathbf{x} \in \text{Local}, \quad \nabla \cdot \mathbf{J}(\mathbf{x}) \gg 0
$$

---

## 3. Theory of Entropic Elasticity [Ref: Note #7]

A regional economy behaves as an **Elastic Body**, not an infinite container.

### 3.1 Hooke's Law of Economics
When external budget injection $S_{in}$ exceeds the local capacity $C_{pot}$, the system generates a **Restoring Force ($F_{eject}$)** that expels excess energy.

$$
\mathbf{F}_{eject} = -k (S_{in} - C_{pot})
$$

*   $k$: **Institutional Rigidity Constant**. A high $k$ (lack of local vendors/bureaucracy) causes violent rejection of capital, forcing it to bounce back to central contractors.

### 3.2 The Theorem of Leakage
If the injection speed exceeds the adaptation speed of the capacity, the retention rate approaches zero.

$$
\frac{dS_{in}}{dt} \gg \frac{dC_{pot}}{dt} \implies \lambda \to 1.0 \quad (\text{Total Ejection})
$$

---

## 4. Thermodynamic Limit of Growth [Ref: Note #6]

As system complexity ($A$) increases, the maintenance cost (Management Entropy) scales non-linearly.

### 4.1 Modified Growth Equation
$$
\dot{K} = s A^\sigma K^\alpha - \underbrace{\delta_0 A^\gamma K}_{\text{Complexity Cost}}
$$

*   $A$: Scale of Intelligence/Urbanization (Complexity).
*   $\gamma$: **Complexity Penalty Coefficient**.
    *   Centralization (Tokyo) and Digital Sprawl increase $\gamma$.
*   **Heat Death Condition:** When $\gamma \ge \sigma$, growth is thermodynamically cancelled by maintenance costs, leading to stagnation.

---

## 5. Extended Metrics for Physical Auditing

### 5.1 Fund Rotation Ratio ($R_{fund}$) [Ref: Case Study 001]
A metric to measure the "Metabolic Rate" of a government.

$$
R_{fund} = \frac{\text{Total Fund Balance}}{\text{Total Annual Revenue}}
$$

*   $R_{fund} \gg 0.4$: **Metabolic Stagnation** (e.g., Tokyo). Wealth is frozen; liquidity trap.
*   $R_{fund} \approx 0.15$: **Healthy Circulation** (e.g., Aichi). Wealth is actively working.

### 5.2 Physical Security Barrier ($Cost_{total}$) [Ref: Note #8]
The firewall mechanism in G-Cart based on "Gravity."

$$
Cost_{total} = P_{bid} + \alpha \cdot (\text{Distance})^2
$$

*   By adding a cost proportional to the **square of physical distance**, the algorithm prevents predatory dumping by remote central capital, enforcing local thermodynamic optimization.

---

## 6. G-Cart Control Algorithm

Based on the physics above, the G-Cart protocol enforces the following inequality for all budget executions:

### The Impedance Matching Condition
$$
I(t) \le \frac{dC_{pot}}{dt}
$$

*   **Function:** Throttles the budget injection rate $I(t)$ to match the local capacity growth rate.
*   **Objective:** Prevents "Elastic Rebound" (Leakage) and induces "Plastic Deformation" (Permanent Industrial Growth).
