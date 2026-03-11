---
title: " CVEMapper [In Progress]"
excerpt: " Automated CVSS Severity Prediction <br>"

collection: portfolio
---

## AI Focus Area
NLP | SecBERT | Vulnerability Intelligence | CVSS | NVD | HuggingFace | Gradio  

## Overview
CVEMapper fine-tunes SecBERT on CVE description text to predict CVSS v3 severity class (Low / Medium / High / Critical) and optionally the raw base score, enabling automated and consistent triage at scale.

## Technical Implementation
- Pulling 160,000+ CVE records via the NVD API with temporal train/validation/test splits to prevent data leakage
- Establishing non-deep-learning baselines (TF-IDF + Logistic Regression, TF-IDF + Random Forest) for comparison
- Fine-tuning SecBERT with a classification head; hyperparameter search over learning rate and max sequence length
- Adding a regression head to predict raw CVSS base scores; comparing MAE vs. classification ordinal accuracy
- Explainability layer: token attribution visualizations to identify which words drive Critical predictions
- CWE-stratified error analysis and vendor bias study to understand model failure modes
- Gradio demo deployed on HuggingFace Spaces — paste a CVE description, get a severity distribution


## Tech Stack
SecBERT · HuggingFace Transformers · PyTorch · NVD API · scikit-learn · Gradio · HuggingFace Spaces · Python