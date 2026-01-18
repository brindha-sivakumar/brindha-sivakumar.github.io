---
title: "PoliteMeter"
excerpt: "Automated politeness detection"
collection: portfolio
---

## AI Focus Area
Natural Language Processing (NLP) | Text Classification | Transformer Models

## Overview
Developed and compared multiple machine learning approaches including classical ML, deep learning, transformers, and rule-based reasoning, for detecting politeness level in text.

## Technical Implementation
### Support Vector Machine (Baseline)
- TF-IDF vectorization with unigram + bigram analysis
- Linear kernel with balanced class weighting
- 68.43% test accuracy with minimal computational overhead
- Strong performance: 89% recall on impolite class, interpretable feature weights

### LSTM Deep Learning
- Custom architecture: 100-dim embeddings, 256 hidden units, 2 layers, 2.7M parameters
- Systematic hyperparameter tuning across 7 configurations
- Identified overparameterization issue: 308 params/sample caused model collapse
- Critical insight: Deep learning requires 5-10× more data for this task complexity

### BERT Transformer (Transfer Learning)
- Fine-tuned bert-base-uncased (110M pre-trained parameters)
- Implemented early stopping strategy based on validation performance
- 68.16% accuracy at 2 epochs (optimal), degraded to 63.05% at 10 epochs
- Demonstrated transfer learning effectiveness on small datasets (<11K samples)

### Rule-Based Expert System
- Engineered linguistic features: modal verbs, gratitude markers, hedges, imperatives
- Scoring algorithm with confidence weighting
- Provides transparent baseline for ensemble voting

### Weighted Ensemble System
- Probabilistic voting across SVM (0.50), BERT (0.30), Rules (0.20)
- Tested 4 weight configurations to optimize complementary strengths
- 69.2% final accuracy - best overall performance

### Data Engineering
- Stanford Politeness Corpus: 10,956 samples from Wikipedia Talk + Stack Exchange
- Handled severe class imbalance (65.9% / 20.3% / 13.8% distribution)
- Implemented stratified sampling and inverse frequency class weighting
- Preprocessing pipeline: normalization, tokenization, label categorization

## Key Achievements
- 69.2% accuracy with ensemble system, outperforming individual models
- Demonstrated that traditional ML (SVM) matched transformer performance (68.43% vs 68.16%) for this task class
- Identified critical early stopping point for BERT (2 epochs optimal; 5% degradation by epoch 10)

## Skills Demonstrated

### NLP & Deep Learning
- Frameworks: PyTorch, Hugging Face Transformers, NLTK
- Techniques: Transfer learning, fine-tuning, embedding layers, sequence modeling
- Models: LSTM networks, BERT transformers, attention mechanisms

### Traditional ML
- Algorithms: Support Vector Machines, feature vectorization
- Feature Engineering: TF-IDF, n-gram analysis, linguistic pattern extraction
- Libraries: scikit-learn, pandas, NumPy

### Model Evaluation & Optimization
- Hyperparameter tuning with systematic configuration testing
- Cross-validation and stratified train/test splits
Confusion matrix analysis and per-class performance metrics
- Early stopping criteria and overfitting detection

## Critical Insights for Production
## Model Selection Guidelines:
- Simple keyword-driven tasks → Traditional ML (SVM) optimal
- Limited data (<10K samples) → Transfer learning (BERT) or SVM
- Interpretability required → SVM or rule-based systems
- Maximum accuracy needed → Ensemble methods (+0.77 pp gain)

## Deployment Tradeoffs:
- SVM: 1ms inference, 1MB memory, CPU-only, high interpretability
- BERT: 50ms inference, 440MB memory, GPU recommended, black-box
- Ensemble: Best accuracy, moderate resources, component transparency

## Applications
- Content Moderation: Real-time politeness scoring for online communities
- Customer Service: Automated quality analysis of support interactions
- Communication Tools: Email/chat assistants with tone suggestions
- Professional Development: Writing feedback systems for workplace communication

## Links
- [GitHub Repository](https://github.com/brindha-sivakumar/PoliteMeter/tree/main)
