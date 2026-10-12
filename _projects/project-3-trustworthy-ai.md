---
title: "Trigger Generalization and Defense Evasion in Backdoored CNNs"
excerpt: "Stress-testing backdoor defenses in CNNs across trigger configurations <br> - Attacks: fixed patch, blended, and shifted-patch triggers (BadNets-style) <br>
- Defenses: Activation Clustering, Fine-Pruning <br>
- Stack: PyTorch, CIFAR-10, ResNet-18"
collection: portfolio

---

## AI Focus Area
Adversarial ML | Backdoor Attacks | CNN | Defense Evasion | PyTorch | CIFAR-10

## Overview
Deep neural networks deployed in safety-critical systems are vulnerable to backdoor attacks, a form of training-time manipulation where a model behaves normally on clean inputs but misclassifies any input containing a specific trigger pattern. This team project (4 members) empirically investigated which trigger configurations generalize best and under what conditions two standard defenses, Activation Clustering and Fine-Pruning, fail.

## Technical Implementation
- Trained a clean CIFAR-adapted ResNet-18 baseline on CIFAR-10 (95.3% test accuracy) as the reference for all backdoored models
- Implemented BadNets-style attacks with three trigger types (fixed patch, blended noise, shifted patch) and swept 27 configurations across poison ratios of 1%, 5%, and 10%
- Implemented Activation Clustering (PCA + k-means on penultimate-layer activations) and Fine-Pruning (channel pruning of the final residual block at 10-90%) and evaluated them on the backdoored models
- Ran a 20-configuration adaptive blended-trigger sweep (blend strength ε × poison ratio) to map where attacks evade Activation Clustering while keeping high attack success

## Key Achievements
- All 27 configurations exceeded 96% attack success rate (ASR) while clean accuracy stayed in the 93-94% range, versus the 95.3% baseline
- Blended triggers were the most sample-efficient: above 99.5% ASR at 1% poison and effectively 100% at 5% and 10%
- Shifted-patch triggers closely matched fixed-patch results, showing the model learns the trigger pattern rather than a pixel location
- Fine-Pruning was strongly configuration-dependent: it cut ASR to 7% for a strong blended-trigger model at 10% pruning, but only partially and non-monotonically suppressed patch triggers
- In the adaptive sweep, 9 of 20 configurations evaded our Activation Clustering implementation, and 8 did so while keeping ASR at or above 90%. Several 5% poison configurations evaded with ASR above 99.7%, because the detector's minority-cluster assumption broke down

## Skills Demonstrated
### AI/ML Technologies
- Adversarial ML: data poisoning, backdoor attack design, trigger generalization analysis
- Defense implementation: Activation Clustering, Fine-Pruning
- Deep Learning: PyTorch, ResNet-18 adaptation for CIFAR-10 (SGD with Nesterov momentum, cosine annealing)

### Cybersecurity Domain
- Training-pipeline and ML supply-chain threat modeling
- Defense evaluation and evasion analysis from an adversary's perspective

### Data Science
- Controlled experiment design (27-configuration sweep and 20-configuration adaptive grid)
- Evaluation metric design (clean accuracy, ASR, detection outcome)
- Results analysis and visualization (ASR/CA heatmaps, trade-off curves) with Matplotlib

## Links
- [Research Paper](/assets/papers/backdoor-cnn-trigger-generalization.pdf)