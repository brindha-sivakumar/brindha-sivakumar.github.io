---
title: "CVEMapper: Predicting CVSS v3 Severity from CVE Text with SecBERT"
excerpt: "Fine-tuning a security-domain transformer to predict vulnerability severity under a temporal split <br> - Task: 4-class CVSS v3 severity (Low, Medium, High, Critical) from NVD descriptions <br>
- Models: TF-IDF baselines, SecBERT, bert-base-uncased ablation, regression head <br>
- Stack: PyTorch, HuggingFace Transformers, NVD API, Google Colab"
collection: portfolio

---

## AI Focus Area
NLP | Transformers | Vulnerability Management | Class Imbalance | Temporal Evaluation | PyTorch

## Overview
CVSS severity scores guide how security teams prioritize patching, but scoring is largely manual. This project tests whether a transformer fine-tuned on CVE text can predict CVSS v3 severity accurately enough to assist manual scoring. The evaluation is a temporal split, so the model is tested on CVEs published after everything it trained on.

## Technical Implementation
- Fetched about 341K CVEs from the NVD API with retry and backoff on rate limits, and parsed 246,920 records with CVSS v3 scores
- Split by publication date: train on 2015-2021 CVEs (80,253), hold out 2022-2024 CVEs (152,514) as a blind test set, plus a 14,162-row random validation holdout. Added assertions to check for leakage
- Handled severe class imbalance (LOW is 2.3% of training data) with inverse-frequency class weights in a custom `WeightedTrainer`
- Built TF-IDF + Logistic Regression and TF-IDF + Random Forest baselines for comparison
- Fine-tuned `jackaduma/SecBERT` (first run: lr=2e-5, max_len=256, 5 epochs, T4 GPU), then ran a 6-configuration grid search over learning rate and max sequence length
- Ran a `bert-base-uncased` ablation under the best config to measure the benefit of security-domain pre-training
- Trained a regression head on the raw CVSS score and compared it against classification
- Replaced `trainer.predict()` with a plain PyTorch DataLoader loop to evaluate reliably on the 152K-sample test set

## Key Achievements
- Showed that random validation overstates performance: F1-weighted fell from 0.765 (val) to 0.583 (2022-2024 blind test) for SecBERT, from 0.740 to 0.583 for Random Forest, and from 0.648 to 0.534 for Logistic Regression
- SecBERT beat TF-IDF + Random Forest by 2.4 points on validation (0.765 vs 0.740) but tied it on the blind test (0.583 vs 0.583), with slightly higher macro-F1 (0.442 vs 0.426)
- Grid search over learning rate and sequence length found learning rate mattered most (0.713 at 1e-5 vs 0.743 at 5e-5); max_len changed results by under 0.01
- A bert-base-uncased ablation matched or beat SecBERT (0.766 vs 0.743 under the same 3-epoch config), so I found no evidence that security-domain pre-training helped on this task
- The LOW class (2.3% of training data) stayed the weakest: test F1 of 0.09 for SecBERT even with 10.9x class weighting

## Skills Demonstrated
### AI/ML Technologies
- Transformer fine-tuning: HuggingFace Trainer, custom loss and prediction steps, class-weighted cross-entropy
- Experiment design: hyperparameter grid search, domain pre-training ablation, regression vs. classification comparison
- Imbalanced classification and overfitting diagnosis (validation loss vs. F1 divergence)

### Cybersecurity Domain
- NVD / CVE / CVSS data pipelines and severity scoring
- Vulnerability prioritization as an ML problem

### Data Science
- Temporal train/test splitting and leakage checks
- Large-scale data collection with rate-limit handling
- Reproducible training on a two-machine setup (local + Colab) with pinned dependencies