# Compositional-Data-Analysis
G-TRACE is a high-precision framework for Compositional Data Analysis (CoDA), measuring structural shifts relative to a defined baseline. By leveraging Aitchison Geometry via CLR-transformation, it eliminates the "constant sum constraint" and preserves multivariate relationships.
# G-TRACE Professional: Dynamic Geometric Stability Analysis

**G-TRACE** is a high-precision R framework designed for **Compositional Data Analysis (CoDA)**. It quantifies the structural stability of multivariate systems by measuring geometric shifts relative to a user-defined reference baseline. By leveraging **Aitchison geometry**, G-TRACE provides robust insights into system integrity and anomaly detection.

## 🚀 Key Features

- **CLR Transformation:** Standardizes compositional data to eliminate the "constant sum constraint" and handle multivariate relationships accurately.
- **Manual Baseline Selection:** Allows users to set a specific reference sample (e.g., Control Group or Time-Zero) for relative comparison.
- **Baseline Reliability Scoring:** Evaluates if the chosen reference is statistically representative or a potential outlier using Aitchison distance.
- **Geometric Stability Index (GSI):** A proprietary metric ($e^{-LRMSD}$) quantifying structural preservation; scores near 1.0 indicate high stability.
- **Automated Anomaly Detection:** Pinpoints significant departures from the baseline using a robust **MAD-based (Median Absolute Deviation)** threshold.
- **Stability Confidence Index:** Determines the presence of a reliable "Invariant Anchor" within the system.

## 🛠️ Implementation

### 1. Requirements
- **R Environment**: Basic installation (No external libraries required for core logic).
- **Data Input**: A matrix or dataframe named `Dataset` (Rows: Samples, Columns: Components).

### 2. Quick Start
1. Define your data as `Dataset`.
2. Set your `target_baseline_idx` (Line 7) to your desired reference index.
3. Run the script to generate the analytical report and dual-pane visualizations.

## 📊 Interpretation Logic

- **Stability Confidence > 5.0**: **HIGH CONFIDENCE**. The system contains strong invariant anchors for reliable referencing.
- **Stability Confidence < 2.0**: **LOW CONFIDENCE**. The system exhibits widespread fluctuation; no stable reference point exists.
- **Pro-Tip**: The report automatically identifies the most "geometrically central" sample, which may serve as a more representative baseline.

## 📈 Visual Outputs
- **GSI Trajectory**: Tracks systemic stability across the sample sequence, highlighting the baseline (Blue) and anomalies (Red).
- **Top Invariant Components**: Visualizes the log-ratio shift of the most stable components to reveal subtle structural fingerprints.
