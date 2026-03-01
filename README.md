# Graph-Based Anti-Money Laundering (AML) Detection System

## Overview

This project implements a graph-based Anti-Money Laundering (AML) detection framework designed to identify structural fraud behaviors within large-scale transaction networks. The system simulates realistic financial transactions, injects fraud patterns, and applies network analytics to detect suspicious accounts.

The framework models transactions as a directed graph and integrates structural fraud indicators with centrality measures to compute a composite AML risk score.

---

## Fraud Patterns Modeled

The system detects three structural money laundering behaviors:

1. **Structuring (Burst Pattern)**  
   Multiple small-value transactions within a short time window to evade reporting thresholds.

2. **Layering (Multi-Hop Chains)**  
   Sequential transaction chains (A → B → C) used to obscure the origin of funds.

3. **Circular Transactions (3-Cycles)**  
   Closed-loop fund transfers where money returns to the originating account.

---

## System Architecture

1. Synthetic transaction generation
2. Directed graph construction using NetworkX
3. Structural fraud detection (S, L, C flags)
4. Network centrality computation (PageRank + Degree)
5. Composite AML risk scoring
6. Threshold-based alert generation
7. Performance evaluation and robustness analysis

---

## AML Risk Model

The AML risk score is computed as:

AML_Risk =  
0.35 * Structuring  
+ 0.30 * Layering  
+ 0.15 * Circular  
+ 0.20 * Normalized Centrality  

This produces a continuous risk score per account.

---

## Evaluation Metrics

The system is evaluated using:

- Precision
- Recall
- F1 Score
- ROC Curve (AUC)
- Precision–Recall Curve
- Confusion Matrix
- Threshold Sensitivity Analysis
- Feature Ablation Study
- Noise Robustness Testing

---

## Key Results

- Strong class separability (AUC ≈ 1.0 in synthetic environment)
- High precision with controlled false positives
- Layering and circular detection contribute most significantly to performance
- Stable F1 across moderate threshold variations
- Gradual degradation under injected risk noise

---

## Scalability

Graph construction performance was evaluated across increasing transaction sizes, demonstrating near-linear scalability.

---

## Project Structure

Single Python workflow includes:

- Data simulation
- Graph construction
- Fraud detection logic
- Risk scoring
- Evaluation metrics
- Visualization outputs

---

## How to Run

1. Install dependencies (see requirements.txt)
2. Run the Python script or notebook
3. Outputs include:
   - Fraud subtype graphs
   - Risk distribution plots
   - ROC & PR curves
   - Confusion matrix
   - Robustness analyses

---

## Notes

This project operates in a controlled synthetic environment. Performance metrics reflect internal validation against injected fraud behaviors.

---

## Authors
Aditya Manoj , Anika Gupta , Anjali Ashtankar , Ayaan Banatwalla
Group 2 – AML Graph-Based Detection Project
