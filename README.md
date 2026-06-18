# Microrobot Navigation in Vascular Networks
Comparative study of bio-inspired and deterministic pathfinding algorithms for autonomous microrobot navigation in vascular networks, with application to targeted drug delivery.

## Context
Independent project developed as part of a Biomedical Engineering portfolio at Instituto Superior Técnico, Universidade de Lisboa.

## Overview
This project models the vascular system as a directed graph with biological properties (vessel diameter, length, and blood flux direction) and compares two pathfinding algorithms:

- **A\*** - deterministic algorithm, guarantees optimal path
- **ACO (Ant Colony Optimization)** - bio-inspired algorithm based on pheromone trails

Edge costs are computed using **Poiseuille's Law** (R = 8ηL / πr⁴), which models blood flow resistance as a function of vessel diameter and length - heavily penalizing narrow vessels.

## Key Results

|   Graph   | Cost Model | Algorithm | Path Cost | Time (s) |
|-----------|------------|-----------|-----------|----------|
| 500 nodes |   Simple   |     A*    | **32.9**  |  0.0007  |
| 500 nodes |   Simple   |    ACO    | **31.11** |  0.1366  |
| 500 nodes | Poiseuille |     A*    | **82.83** |  0.0008  |
| 500 nodes | Poiseuille |    ACO    | **127.94**| 0.0980  |

**Main finding:** The cost model determines which algorithm wins. With Poiseuille's law, A* outperforms ACO. With a simpler cost model, ACO finds lower-cost paths by exploring more alternatives.

## Stack
Python · NetworkX · NumPy · Matplotlib

## Paper
Full methodology, results and discussion available in `paper_final/`.
