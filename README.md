# Hadi Abdollahzadeh

**Researcher in AI, Mathematical Optimization, Smart Grids, and Energy Systems**

Researcher specializing in physics-informed machine learning, mathematical optimization, and demand-side flexibility in modern power networks. My work focuses on deep imitation learning architectures that bridge clairvoyant optimization experts with real-time prosumer energy management under operational and physical grid constraints.

---

## Research Focus

- **Physics-Informed Machine Learning**: Embedding physical laws, domain dynamics, and boundary penalties into neural objective functions.
- **Deep Imitation Learning (IL)**: Designing high-fidelity neural policies supervised by clairvoyant mathematical optimization experts.
- **Mathematical Optimization**: Formulating Linear Programs (LP) with provable continuous relaxation exactness under physical battery boundaries.
- **Smart-Grid Energy Management**: Coordinating distributed energy resources (DERs) to mitigate peak demand and distribution transformer loading.
- **Residential Prosumer Systems**: Optimizing behind-the-meter rooftop photovoltaic (PV) generation and flexible electric vehicle (EV) storage.
- **EV Charging Optimization**: Developing real-time charging and vehicle-to-grid (V2G) strategies under volatile dynamic tariffs.
- **Demand-Side Flexibility**: Activating flexible storage loads for demand response and distribution grid support.
- **Reproducible Scientific Computing**: Developing modular, containerized, and certified research repositories for peer-reviewed academic publication.

---

## Featured Research

### [Physics-Informed Cost-and-Boundary-Aware Deep Imitation Learning for Residential EV Charging](https://github.com/hadi-zadeh/physics-informed-ev-charging)

*Manuscript prepared for **IEEE Transactions on Smart Grid***  
**Authors**: Hadi Abdollahzadeh, Morteza Mollajafari  
**Repository**: [`hadi-zadeh/physics-informed-ev-charging`](https://github.com/hadi-zadeh/physics-informed-ev-charging)

Conventional deep imitation learning policies trained with uniform behavior cloning (BC) treat action errors equally across volatile electricity tariffs and generate unconstrained raw actions that frequently violate battery operating boundaries, causing severe downstream safety-projection trajectory drift. 

This research proposes a composite imitation learning framework combining:
1. **Clairvoyant LP Expert Supervision**: Generating global cost-optimal charge/discharge schedules using the COIN-OR Clp simplex solver engine via Python-MIP, with continuous LP relaxation exactness guaranteed by Theorem 1.
2. **Differentiable Soft Training Guidance (`CompositeImitationLoss`)**: Dynamically scaling policy imitation gradients by normalized electricity tariffs ($\lambda_{\mathrm{tariff}} = 0.10$) and penalizing predicted battery State-of-Charge (SoC) boundary violations ($\lambda_{\mathrm{boundary}} = 0.05$).
3. **Deterministic Hard Runtime Feasibility (`SafetyPostProcessor`)**: Guaranteeing that physical battery capacity limits, distribution transformer limits, and $100\%$ departure SoC fulfillment are strictly enforced at runtime.

### Key Results (Frozen 180-Scenario Evaluation across 5 Independent Seeds)

All results are certified over 180 frozen out-of-sample test scenarios spanning CAISO, PJM, and UK Power Networks (2,532 active dwell hours):

| Metric / Parameter | Baseline Behavior Cloning (B0) | Proposed Method (E2) | Clairvoyant Reference (LP) | Evaluation Outcome |
| :--- | :---: | :---: | :---: | :---: |
| **Total Electricity Cost** | $201.08 ± $2.32 | **$199.00 ± $2.29** | $199.50 | -$2.08 / EV (Near-LP Parity) |
| **Action Boundary Correction** | 1,139.67 ± 659.43 kWh | **754.33 ± 221.41 kWh** | 0.00 kWh | **33.81% reduction** ($p = 1.04 \times 10^{-19}$) |
| **Feasibility Win Rate** | 15.00% | **85.00%** | — | 153/180 scenarios improved |
| **Cost Win Rate** | 28.33% | **71.67%** | — | 129/180 scenarios improved |
| **Measured Pipeline Latency** | 0.628 ms/step | **0.738 ms/step** | ~12,500 ms (Offline LP) | Sub-millisecond execution |
| **Trainable Parameters** | 216,321 | **216,321** | — | Identical LSTM footprint |
| **Departure SoC Fulfillment** | 100.0% | **100.0%** | 100.0% | Strict fulfillment via SPP Step 2 |

*Statistical Significance (Paired Proposed E2 vs. Baseline B0)*:
- Action Boundary Correction Energy reduction: **33.81%** on the frozen evaluation (Wilcoxon $p = 1.0365 \times 10^{-19}$, paired Cohen's $d_z = -0.745$).
- Electricity cost difference: Wilcoxon $p = 2.5313 \times 10^{-8}$ (paired Cohen's $d_z = -0.366$).

---

## Selected Public Projects

The following public repositories are actively maintained on this profile:

- **[`physics-informed-ev-charging`](https://github.com/hadi-zadeh/physics-informed-ev-charging)**  
  Official research repository for physics-informed composite imitation learning for residential EV charging in solar prosumer systems. Includes complete models, composite loss functions, deterministic 3-step SPP, scenario datasets, and one-command verification suite.  
  *Technical Area*: Physics-Informed ML • PyTorch • Python-MIP • Smart Grids

- **[`V2G`](https://github.com/hadi-zadeh/V2G)**  
  Vehicle-to-Grid (V2G) power dispatch and charging coordination algorithms for electric vehicles participating in residential energy management.  
  *Technical Area*: V2G Systems • Energy Management • Optimization

- **[`CARLA_tutorial`](https://github.com/hadi-zadeh/CARLA_tutorial)**  
  Tutorial implementations, simulation assets, and control environments for autonomous vehicle testing using the open-source CARLA simulator.  
  *Technical Area*: Autonomous Driving • Simulation • CARLA

- **[`PCB-Design-and-Simulation-in-Altium`](https://github.com/hadi-zadeh/PCB-Design-and-Simulation-in-Altium)**  
  Hardware engineering projects, schematic design, and circuit simulation implementations developed using Altium Designer.  
  *Technical Area*: Hardware Engineering • PCB Design • Altium Designer

- **[`bibliography`](https://github.com/hadi-zadeh/bibliography)**  
  Academic research utility for processing and converting Zotero CSV exports into standardized citation bibliographies.  
  *Technical Area*: Academic Tooling • Jupyter Notebook • Python

---

## Publications & Manuscripts

- **Physics-Informed Cost-and-Boundary-Aware Deep Imitation Learning for Residential EV Charging in Solar Prosumer Systems**  
  Hadi Abdollahzadeh, Morteza Mollajafari  
  *Manuscript prepared for IEEE Transactions on Smart Grid*  
  Companion Code & Data: [`hadi-zadeh/physics-informed-ev-charging`](https://github.com/hadi-zadeh/physics-informed-ev-charging)

---

## Technical Stack

- **Machine Learning & Deep Learning**: Python, PyTorch, TorchVision, NumPy, SciPy, Pandas, Matplotlib
- **Mathematical Optimization**: Python-MIP, COIN-OR CBC / Clp Simplex Engine, Continuous Linear Programming (LP)
- **Domain Areas**: Smart Grids, Electric Vehicle Charging (V1G/V2G), Solar Prosumer Systems, Demand-Side Flexibility
- **Hardware & Simulation**: Altium Designer (PCB Design), CARLA Simulator (Autonomous Systems)
- **Scientific Workflow**: Git, GitHub, LaTeX, Jupyter Notebook, Linux, Windows

---

## Contact & Public Profiles

- **GitHub**: [`github.com/hadi-zadeh`](https://github.com/hadi-zadeh)
- **Public Contact Email**: `research.hadi.ab@gmail.com`
- **Institutional Academic Email**: `hadi_abdollahzadeh@auto.iust.ac.ir`

*Note*: Additional academic links (Google Scholar, LinkedIn, and ORCID) will be integrated directly upon formal manuscript publication.
