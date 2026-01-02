F1 Lap-Time Optimization via Telemetry-Based Sensitivity Analysis
Overview

This project explores how small, localized changes in vehicle speed affect total lap time using public Formula 1 telemetry data. Rather than predicting lap time with a black-box model, I reconstruct lap time from first principles and apply controlled perturbations to ask a simpler but deeper question: where, why, and how do small changes actually matter?

The goal is educational and exploratory — to demonstrate how physics, applied math, and data analysis interact in a real performance system, and to build a framework that others can extend.

Motivation

Motorsport analytics is typically inaccessible, locked behind proprietary tools and teams. I wanted to understand lap-time performance in a way that is transparent, reproducible, and grounded in physical reasoning. This project focuses on sensitivity analysis because it reveals structure and constraints in the system, rather than optimizing blindly.

Method Summary

Telemetry data is loaded using FastF1 and converted to a distance-based representation.
Lap time is reconstructed numerically using time = distance / velocity
Local speed perturbations (±2–5%) are applied over fixed-distance windows.
The resulting change in total lap time is measured to build a sensitivity map.
Additional experiments compare corners vs straights, gains vs losses (asymmetry), and the effect of tire degradation.
This approach prioritizes interpretability over prediction accuracy.

Key Experiments

Lap Time Reconstruction: Verified that numerical integration reproduces official lap times within small error.
Sliding-Window Sensitivity Map: Identified localized regions where small speed changes disproportionately affect lap time.
Final Sensitivty Analysis: Consolidated all perturbation tests to rank segments by marginal lap-time impact under realistic constraints.
Lap-Time Sensitivity Model: Formalized the relationship between local speed perturbations and global lap time using repeatable, parameterized experiments.
Corner vs Straight Comparison: Showed that corners offer higher upside but greater variance than straights.
Asymmetry Test: Found that losses are slightly more costly than equivalent gains are beneficial.
Global Sensitivity Plot: Visualized baseline, perturbed, and degraded lap-time responses across the full circuit to contextualize local effects globally.
Tire Degradation Model: Demonstrated how early inefficiencies compound nonlinearly over a lap.

Figures for these experiments are included in the portfolio.

What I Learned

This project shifted my thinking from global optimization to local sensitivity and constraint-aware reasoning. I was surprised by how often intuitive assumptions (e.g., “straights matter most”) failed under quantitative testing. The process reinforced the importance of modeling choices, spatial framing, and iterative experimentation when working with complex systems.

How to Run

Install dependencies: fastf1, numpy, pandas, matplotlib.
Open 01_data_collection.ipynb.
Run all cells top-to-bottom.
No manual configuration is required.

Notes on Authorship

ChatGPT was used for debugging assistance and brainstorming. All modeling decisions, experimental design, analysis, and interpretation are my own.

Future Work

Possible extensions include multi-lap simulation, pit strategy modeling, probabilistic sensitivity analysis, and richer tire and driver behavior models.