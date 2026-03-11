---
title: "Trigger Generalization and Defense Evasion in Backdoored CNNs [In Progress]"
excerpt: "
- BadNets / backdoor poisoning — injecting malicious behavior at training time <br>
- Trigger generalization — how attack effectiveness changes with trigger design choices <br>
- Adaptive attacks — designing attacks that know and exploit the defense strategy <br>
- Defense robustness — understanding where AC and Fine-Pruning are systematically brittle"

collection: portfolio
---

## AI Focus Area
Adversarial ML | Backdoor Attacks | CNN | Defense Evasion | PyTorch | CIFAR-10

## Overview
Deep neural networks deployed in safety-critical systems are vulnerable to backdoor attacks, that are a form of training-time manipulation where a model behaves normally on clean inputs but misclassifies any input containing a specific trigger pattern. This project systematically investigates which trigger configurations generalize best across settings and under what conditions standard defenses fail.

## Technical Implementation
- Implementing BadNets-style backdoor attacks on CIFAR-10 with a ResNet-18 backbone
- Running a grid search over poison ratio, trigger patch size, and blending strength (epsilon) to map attack surface
- Evaluating two defenses: Activation Clustering (AC) and Fine-Pruning against all trigger configurations
- Designing adaptive evasion strategies that identify the weakest defense conditions
- Producing a reproducible benchmark with full results tables and a clean GitHub repo


## Tech Stack
 PyTorch · CIFAR-10 · ResNet-18 · Activation Clustering · Fine-Pruning · Python · Matplotlib
