The Real-World Humanitarian Problem

During major crises (earthquakes, cyclones, floods, tsunamis), emergency logistics face three brutal realities:

Critical Infrastructure Disruption: Secondary shocks and floods wash out bridges and block transit arteries, rendering standard navigation algorithms invalid.
Exponential Mortality Beyond Survival Windows: Human survival curves are non-linear; delivery delays beyond the critical window (
) lead to preventable loss of life.

The Computational Dilemma in Emergency Response:
Exact Solvers (Integer Linear Programming): Take minutes to hours to converge on NP-hard combinatorial route networks—far too slow when immediate deployment must happen within 60 seconds of disaster notification.
Simple Heuristics (Nearest-Neighbor / First-Come): Run in milliseconds, but exhaust local stockpiles prematurely, leaving remote or highly severe zones with catastrophic unmet demand.

Why Made AegisRelief?
I created AegisRelief to bring the mathematical optimization framework from your research paper—"A Hybrid Linear Programming, Greedy Heuristic, and Genetic Algorithm Framework for Optimal Resource Allocation in Disaster Response" by Taresh Atrey—into a functional, real-world command center.
By implementing an Anytime Decision Controller, AegisRelief guarantees that an actionable, feasible dispatch plan is delivered in any time budget (even under 1 millisecond), and continuously refines that plan as computation time permits.
GitHub README.md Content
Below is the complete markdown content now saved to your project's /README.md:
code

# AegisRelief: Global Disaster Management & Resource Optimization Matrix

[![Live Application](https://img.shields.io/badge/Live%20Demo-Online-00f0ff?style=for-the-badge&logo=googlecloud)](https://ais-pre-6dnwnf5uyuaxrzbsucrnpn-181736372989.asia-east1.run.app)
[![Framework](https://img.shields.io/badge/React%2019-Vite%208-61DAFB?style=for-the-badge&logo=react)](https://react.dev)
[![3D Graphics](https://img.shields.io/badge/Three.js-WebGL-black?style=for-the-badge&logo=threedotjs)](https://threejs.org/)
[![Styling](https://img.shields.io/badge/Tailwind%20CSS%20v4-38B2AC?style=for-the-badge&logo=tailwind-css)](https://tailwindcss.com/)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg?style=for-the-badge)](LICENSE)

> **AegisRelief** is an interactive, real-time 3D planetary disaster management command center and resource dispatch optimization engine. It is designed and implemented around the mathematical formulation and tri-hybrid optimization framework presented in the research paper:  
> **"A Hybrid Linear Programming, Greedy Heuristic, and Genetic Algorithm Framework for Optimal Resource Allocation in Disaster Response"**  
> *Author: Taresh Atrey*

---

## 🌐 Live URLs

* **Production / Shared Web App:** [https://ais-pre-6dnwnf5uyuaxrzbsucrnpn-181736372989.asia-east1.run.app](https://ais-pre-6dnwnf5uyuaxrzbsucrnpn-181736372989.asia-east1.run.app)
* **Development Environment:** [https://ais-dev-6dnwnf5uyuaxrzbsucrnpn-181736372989.asia-east1.run.app](https://ais-dev-6dnwnf5uyuaxrzbsucrnpn-181736372989.asia-east1.run.app)

---

## 🎯 Purpose: Why Was AegisRelief Built?

During humanitarian catastrophes—such as earthquakes, flash floods, oceanic cyclones, or landslides—disaster response coordinators face three critical logistical challenges:
1. **Severe Infrastructure Breakdown:** Roads, bridges, and mountain transit arteries are blocked or washed away, rendering standard route planning useless.
2. **Strict Survival Windows:** Victims trapped under rubble, stranded by rising waters, or deprived of potable water experience exponential mortality spikes if relief arrives after their critical time window ($W_i$).
3. **Severe Time-Constraint Trade-offs in Computation:**
   * Traditional exact solvers (Mixed Integer Linear Programming) can take minutes or hours to compute guaranteed optimal schedules—far too slow for the first 60 seconds of a disaster.
   * Simple greedy heuristics are instantaneous but leave significant unmet demand due to shortsighted resource consumption.

### The Solution: The Tri-Hybrid Anytime Framework
**AegisRelief** bridges the gap between academic operational research and real-time humanitarian field logistics. It implements an **Anytime Controller** that guarantees an immediately actionable dispatch plan under **any** computational budget ($B \ge 0$), seamlessly transitioning from:
1. **Sub-millisecond Greedy Priority Triage** (instant first-wave dispatch), to
2. **Continuous Linear Programming (LP) Relaxation** (global mathematical lower-bound baseline), to
3. **Genetic Algorithm (GA) Metaheuristic** (non-convex schedule refinement).

---

## 🏗️ System Architecture

AegisRelief is architected as a high-performance, reactive single-page application built on React 19, TypeScript, and Three.js:
┌────────────────────────────────────────────────────────────────────────┐
│ AegisRelief UI Layer │
│ │
│ ┌────────────────────────┐ ┌────────────────────────────────────┐ │
│ │ 3D Planetary WebGL │ │ 2D Equirectangular Vector Tactical │ │
│ │ (Three.js Earth) │ │ (Custom Canvas Projection) │ │
│ └──────────┬─────────────┘ └─────────────────┬──────────────────┘ │
│ │ │ │
│ └───────────────┬──────────────────┘ │
│ ▼ │
│ Reactive Viewport & Gesture Manager │
│ (Responsive Aspect Scaling • Touch Drag & Pinch-Zoom • HUD Dock) │
└──────────────────────────────┬─────────────────────────────────────────┘
│
┌──────────────────────────────▼─────────────────────────────────────────┐
│ Tri-Hybrid Optimization Engine │
│ │
│ ┌────────────────────────┐ ┌─────────────────┐ ┌─────────────────┐ │
│ │ Algorithm 1: │ │ Algorithm 2: │ │ Algorithm 3: │ │
│ │ Greedy Heuristic │ │ LP Relaxation │ │ Genetic Meta- │ │
│ │ Priority Triage │ │ Continuous Min- │ │ heuristic (GA) │ │
│ │ O(|Z|log|Z| + |Z||D|) │ │ Cost Flow Bound │ │ Chromosome Tour │ │
│ └───────────┬────────────┘ └────────┬────────┘ └────────┬────────┘ │
│ │ │ │ │
│ └────────────────────────┼────────────────────┘ │
│ ▼ │
│ Anytime Decision Controller │
│ B < t_LP ──► Greedy (Tier 1) │
│ t_LP <= B ──► LP Exact (Tier 2) │
│ B >= t_GA ──► GA Refined (Tier 3) │
└───────────────────────────────────────┬────────────────────────────────┘
│
┌───────────────────────────────────────▼────────────────────────────────┐
│ Data & Telemetry Engine │
│ • Great-Circle Haversine Distance Matrix │
│ • Road Impedance & Bridge Blockage Generator │
│ • Real-Time Incident Surveillance & Telemetry Feed │
│ • Mission Report Generator & Print/PDF Formatter │
└────────────────────────────────────────────────────────────────────────┘
code
Code
---

## 🚀 Key Features & Modules

### 1. Real-Time Globe & 2D Tactical Grid Visualizer
* **Three.js 3D WebGL Globe:** Features atmospheric glow, orbital coordinate graticules, interactive disaster epicenters, and animated quadratic Bezier supply arcs connecting strategic depots to disaster zones.
* **Responsive Aspect-Ratio Auto-Scaler:** Dynamically computes camera distance:
  $$Z_{\text{camera}} = Z_{\text{base}} \times \max\left(1.0, \frac{1.05}{\text{aspectRatio}}\right)$$
  guaranteeing the entire globe remains 100% visible on smartphones, tablets, and wide screens.
* **Full Touch & Gesture Engine:** Native support for single-finger planetary rotation, double-finger pinch-to-zoom, and raycast tapping.
* **2D Vector Tactical Grid:** Modeled after international military & disaster emergency command centers, featuring geopolitical region coding, compass graticules, and direct vector corridors.
* **Mobile Split-View Layout:** On tablets and mobile screens, operators can view the globe and live operational panes simultaneously, or switch to dedicated full-screen views.

### 2. Hybrid Solver Lab
* **Live Interactive Controls:** Adjust time budget ($B$), road network damage rate ($\gamma$), severity weight ($\alpha$), demand weight ($\beta$), and scenario matrix scale ($|Z| \times |D|$).
* **Side-by-Side Tri-Method Benchmark:** Evaluates unmet demand percentage, average delivery delay, execution time, and optimality gap.
* **Active Allocation Ledger:** Granular breakdown of metric tons dispatched, road accessibility, transit delays, and delivery costs.

### 3. Crisis Registry & Deep Incident Dossiers
* Real-time ledger of active global incidents (Himalayan Landslides, Brahmaputra Flash Floods, Coastal Cyclones, Rift Earthquakes, Volcanic Outbursts).
* Modal dossier displaying casualty priorities, storm surge / rainfall metrics, structural collapse details, and depot transit times.

### 4. Strategic Mission Reports
* Generates audit summaries comparing total global demand against fulfilled relief tonnage.
* One-click **Print / PDF Export** tailored for field directors and disaster relief agencies (NDRF, FEMA, UN OCHA).

### 5. Interactive Incident Creator
* Direct in-browser incident logger to inject new earthquakes, floods, or landslides with customized coordinates, casualty metrics, and demand requirements.

---

## 🧮 Mathematical Model & Algorithms

### Problem Formulation
Given disaster zones $Z$, supply depots $D$, demands $d_i$, severity indices $s_i \in [1, 3]$, critical survival windows $W_i$, depot capacities $C_j$, and road impedance $a_{ji} \in \{0, 1\}$:

$$\min_{x} \quad \Phi = \sum_{i \in Z} s_i \cdot \max\left(0, \; d_i - \sum_{j \in D} a_{ji} x_{ji}\right) \;+\; \lambda \sum_{i \in Z} \sum_{j \in D} a_{ji} \cdot \frac{x_{ji}}{d_i} \cdot \max\left(0, \; t_{ji} - W_i\right)$$

Subject to:
$$\sum_{i \in Z} x_{ji} \le C_j \quad \forall j \in D$$
$$\sum_{j \in D} a_{ji} x_{ji} \le d_i \quad \forall i \in Z$$
$$x_{ji} = 0 \quad \text{whenever } a_{ji} = 0$$
$$x_{ji} \ge 0 \quad \forall i \in Z, \; j \in D$$

### Algorithmic Pillars
1. **Priority Greedy Heuristic:** Sorts zones using composite triage metric $\text{Score}_i = \alpha (s_i / 3.0) + \beta (d_i / \sum d_k)$ and greedily consumes inventory from the closest intact depot in $< 1$ millisecond.
2. **LP Continuous Relaxation:** Solves the network flow relaxation in polynomial time, producing the global mathematical lower bound against which any heuristic is audited.
3. **Genetic Algorithm (GA):** Evolves chromosome populations across tournament selections, two-point crossovers, and mutations to handle non-linear road congestion and discrete fleet sizing.
4. **Anytime Property Guarantee:** Guarantees that at any point of execution interruption $B$, the system returns the highest-fidelity feasible dispatch plan computed so far without failing or stalling.

---

## 💻 Installation & Local Setup

### Prerequisites
* **Node.js:** v18.0.0 or higher (v20+ recommended). Check with:
  ```bash
  node -v
npm: v9.0.0 or higher. Check with:
code
Bash
npm -v

Step 1: Clone the Repository
Bash
git clone https://github.com/your-username/aegis-relief.git
cd aegis-relief

Step 2: Install Dependencies

Install all required dependencies:
Bash
npm install
(If your local environment flags peer dependency warnings with Vite 8, use npm install --legacy-peer-deps)
Step 3: Run the Development Server

Bash
npm run dev
Open your browser and navigate to:


http://localhost:3000
(Or specify an alternate port if port 3000 is occupied on your system: npm run dev -- --port 3001)

Step 4: Build for Production

Bash
# Compile and optimize for production
npm run build

# Preview the production build locally
npm run preview
📦 Project File Structure
code
Code
├── public/                 # Static assets & tactical vector maps
├── src/
│   ├── components/
│   │   ├── CreateIncidentModal.tsx    # Field incident submission modal
│   │   ├── DepotsView.tsx             # Strategic reserve depot inventory view
│   │   ├── GlobeView.tsx              # Three.js 3D Globe + 2D Tactical Map
│   │   ├── Header.tsx                 # Command center bar & status indicators
│   │   ├── IncidentDetailModal.tsx    # In-depth disaster dossier modal
│   │   ├── IncidentList.tsx           # Triage ledger & filterable cards
│   │   ├── MissionReportModal.tsx     # Strategic mission export & print modal
│   │   ├── ResearchPaperModal.tsx     # Complete paper viewing component
│   │   └── SolverDashboard.tsx        # Tri-hybrid parameter matrix & ledger
│   ├── data/
│   │   └── seedData.ts                # Real-world disaster zones & reserve depots
│   ├── types/
│   │   └── index.ts                   # TypeScript interfaces & mathematical schemas
│   ├── utils/
│   │   └── optimizer.ts               # LP, Greedy, GA & Anytime Controller
│   ├── App.tsx                        # Master layout & responsive split controller
│   ├── index.css                      # Tailwind CSS v4 styling rules
│   └── main.tsx                       # React 19 application entry point
├── index.html                         # HTML5 shell with responsive metadata
├── package.json                       # Dependencies & build scripts
├── tsconfig.json                      # Strict TypeScript compiler options
└── vite.config.ts                     # Vite 8 bundling & path aliases

🛠️ Technology Stack
Core Framework: React 19 + TypeScript
Build System: Vite 8
3D Visualizations: Three.js (WebGL rendering, Custom Shaders, Quadratic Curves)
Styling & HUD: Tailwind CSS v4
Icons & UI Accents: Lucide React
Animation & Interactions: Motion
📄 License & Attribution
Author: Taresh Atrey
Research Paper: "A Hybrid Linear Programming, Greedy Heuristic, and Genetic Algorithm Framework for Optimal Resource Allocation in Disaster Response"
License: MIT
