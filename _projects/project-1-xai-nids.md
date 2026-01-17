---
title: "Explainable AI for Network Intrusion Detection"
excerpt: "Applying Causal Inference and XAI to improve alert prioritization in NIDS"
collection: portfolio
---

## AI Focus Area
Machine Learning for Cybersecurity | Explainable AI | Causal Inference

## Overview
Developed a novel hybrid framework integrating Explainable AI techniques with Causal Inference to improve the interpretability and effectiveness of Network Intrusion Detection Systems (NIDS). This research-oriented project aims to solve the "black box" problem in AI-powered security systems by providing transparency to security analysts with root cause analysis.

## Technical Implementation
- Long Short Term Memory (LSTM) classifier for alert classification (important vs irrelevant)
- DeepLIFT XAI framework selected after evaluating four XAI techniques (DeepLIFT, LIME, SHAP, Integrated Gradients) across various metrics 
- Applied Peter-Clark (PC) and Greedy Equivalence Search (GES) algorithms to construct a consensus causal graph that identifies root causes and causal paths.
- Combined to develop a hybrid framework that synthesized XAI feature importance with causal graph traversal to generate actionable explanations.


## Key Achievements
- Achieved 36% causal coverage demonstrating meaningful XAI-causal integration for alert prioritization
- Demonstrated 70% complementarity between XAI and causal approaches, proving they analyze different but complementary aspects of network threats
- Validated framework across two datasets (TalTech NIDS, UNSW-NB15), confirming robustness and generalizability


## Skills Demonstrated
### AI/ML Technologies 
- Deep Learning: PyTorch, LSTM networks, neural network optimization
- Explainable AI: DeepLIFT, SHAP, LIME, Integrated Gradients 
- Causal Inference: PC algorithm, GES algorithm, causal graph analysis
- ML Frameworks: scikit-learn, pandas, NumPy

### Cybersecurity Domain
- Network intrusion detection systems (NIDS) architecture and operation
- Security alert prioritization and false positive reduction
- Threat detection workflows and SOC (Security Operations Center) analyst requirements
- Network traffic analysis and feature engineering

### Data Science
- Handling severely imbalanced datasets (98.5% / 1.5% split)
- Feature selection and preprocessing (42 network features)
- Statistical analysis and performance metric design
- Data visualization with matplotlib and NetworkX


## Links
- [GitHub Repository](https://github.com/brindha-sivakumar/Hybrid-Causal-XAI-For-NIDs)
- [Research Paper](url) 



## Problem Statement
Traditional NIDS generate high volumes of alerts with limited context, leading to alert fatigue and missed threats. Security analysts need to understand WHY a system flagged something as malicious.

## Approach
- Applied SHAP and LIME for model explanations
- Implemented causal inference to identify true threat indicators
- Built comparative analysis of explanation quality across different ML models

## Technologies Used
- Python, PyTorch, scikit-learn
- SHAP, LIME for explainability
- Network traffic datasets (NSL-KDD, CICIDS2017)

## Results
- Improved alert prioritization accuracy by X%
- Reduced false positive investigation time
- Created interpretable feature importance rankings

## Links
- [GitHub Repository](#)
- [Research Paper](#)
- [Demo Video](#)

