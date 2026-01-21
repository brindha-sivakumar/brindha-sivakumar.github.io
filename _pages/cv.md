---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
---

# Brindha Sivakumar - Curriculum Vitae

## Summary

Graduate student in Artificial Intelligence with **7 years of professional experience** in cybersecurity and infrastructure security. Specializes in implementing robust security measures, automating workflows, and applying AI/ML techniques to solve complex security challenges. Currently pursuing applied research on AI threat landscape with a focus on securing the AI lifecycle, focusing on adversarial robustness against model extraction and training data poisoning within cloud-native infrastructures.

**Unique Value Proposition:** Bridges the gap between AI innovation and cybersecurity operations, bringing both deep technical expertise and practical industry experience to build secure, explainable, and trustworthy AI systems.

---

## Education

### University of Michigan-Dearborn
**Master of Science in Artificial Intelligence**  
*Expected Graduation: May 2027*  
Dearborn, Michigan

**Research Focus:**
- Explainable AI (XAI) for Network Intrusion Detection Systems
- Causal Inference for Security Alert Prioritization
- Deep Learning for Cybersecurity Applications like vulnerable code and credential leakage detection in code
- Enhancing Anomaly Detection through Vector-Based Information Retrieval and Neural Log Analysis.

**Relevant Coursework:**
- Machine Learning & Deep Learning
- Intelligent Systems
- Algorithms Analysis and Design
- Trustworthy AI

### University of Limerick
**Master of Engineering in Information and Network Security**  
*GPA: 3.54/4.0*  
Limerick, Ireland

**Specialization:**
- Network Security Architecture
- Cryptography and Secure Communications
- Data Forensics and Biometrics

### Anna University
**Bachelor of Engineering in Computer Science**  
*GPA: 7.38/10*  
Chennai, India

---

## Professional Experience

### Workday
**Cybersecurity Engineer**  
*January 2023 – October 2024 | Dublin, Ireland*

**Kubernetes Security**

- Designed and developed security policies as guardrails for Kubernetes platforms using **Gatekeeper with Open Policy Agent (OPA)**, enforcing best practices across microservices
- Implemented policy-as-code framework using **Rego**, reducing manual security reviews by 60% and ensuring consistent security standards across development teams
- Collaborated with platform engineering teams to integrate security controls into CI/CD pipelines, enabling shift-left security practices

**Cloud Security and DevSecOps**

- Developed Python-based solution to identify and remediate unused IAM roles across large-scale AWS organization
- Performed security reviews of application code changes using Infrastructure as Code (IaC) and CI/CD pipelines

**Key Technologies:** Kubernetes, OPA/Gatekeeper, Rego, Python, Terraform, AWS, Git, CI/CD (Jenkins, GitHub Actions)

---

### Smarttech247
**Security Engineer - Technical Lead**  
*June 2020 – December 2022 | Dublin, Ireland*

**Security Engineering**
- Identified and onboarded high-value asset logs into SIEM platform, enhancing detection coverage for critical systems
- Developed 15+ SOAR (Security Orchestration, Automation, and Response) playbooks for common incident scenarios, streamlining response workflows
- Reduced mean time to resolution (MTTR) by **50%** through automated triage, enrichment, and remediation actions
- Integrated SOAR platform with ticketing systems, SIEM, EDR, and threat intelligence feeds for end-to-end automation
- Participated in 24/7 security operations rotation, responding to security alerts and incidents

**Security Infrastructure Management:**
- Spearheaded deployment, maintenance, and upgrade of enterprise security toolsets including SIEM, SOAR, and UEBA platforms 
- Managed scheduled maintenance windows with 99.9% uptime, ensuring minimal disruption to security monitoring capabilities
- Conducted version upgrades and patch management for security tools, addressing vulnerabilities while maintaining operational stability

**Continuous Improvement & Documentation:**
- Developed automation scripts in Python and Bash for routine security operations tasks, saving 10+ hours per week
- Created comprehensive technical documentation for security procedures, playbooks, and incident response workflows
- Implemented security policies aligned with industry frameworks (NIST, ISO 27001), ensuring compliance and best practices

**Team Leadership & Mentorship**
- Led team of 4 security engineers, managing daily operations and security engineering workflows
- Created executive-level dashboards and KPIs for security metrics reporting to stakeholders

**Key Technologies:** Splunk, IBM QRadar, Palo Alto Cortex XSOAR, CrowdStrike EDR, MISP (Threat Intelligence), Python, Bash

---

### Tata Consultancy Services
**Systems Engineer**  
*November 2016 – August 2019 | Chennai, India*

**Network & Endpoint Security Administration:**
- Administered network security policies across NextGen firewalls (Palo Alto, Fortinet) with 5,000+ endpoints
- Configured and maintained VPN connections between cloud and on-premise infrastructure
- Performed firewall rule reviews and cleanup, reducing rule complexity by 25% and improving performance

**System Hardening & Compliance:**
- Automated system hardening for Windows and Linux servers using PowerShell and Bash scripts based on CIS (Center for Internet Security) benchmarks
- Conducted vulnerability assessments and remediation tracking, maintaining server security posture above 90% compliance


**Key Technologies:** Palo Alto Firewalls, Fortinet, PowerShell, Bash, Symantec Endpoint Protection, Qualys, Windows Server, Linux (RHEL, Ubuntu)

---

## Academic Projects & Research

### Explainable AI for Network Intrusion Detection
**Research Paper | University of Michigan-Dearborn**  
*September 2024 – Present*

- Developed novel hybrid framework integrating **Causal Inference** with **Explainable AI** to improve alert prioritization in Network Intrusion Detection Systems (NIDS)
- Achieved **36% causal coverage** and **70% complementarity** between XAI and causality-based insights, demonstrating meaningful integration
- Built LSTM classifier achieving **99.5% accuracy** for alert classification, outperforming Random Forest (+2.8%) and Logistic Regression (+7.7%)
- Evaluated four XAI techniques (DeepLIFT, LIME, SHAP, Integrated Gradients); selected DeepLIFT with **0.76 faithfulness correlation**
- Applied Peter-Clark (PC) and Greedy Equivalence Search (GES) causal discovery algorithms to construct consensus causal graph
- Validated framework across two datasets (TalTech NIDS, UNSW-NB15), confirming robustness and generalizability
- **Impact:** Enables SOC analysts to understand *what* triggered alerts (XAI), *why* they occurred (causal), and *what actions* to take (recommendations)

**Technologies:** PyTorch, Python, Captum (DeepLIFT, IG), SHAP, LIME, causal-learn, pandas, NetworkX

---

### PoliteMeter: Automated Politeness Detection in Text
**Course Project | University of Maryland (ECE 579)**  
*September 2024 – December 2024*

- Developed and compared five approaches for automated politeness classification: SVM, LSTM, BERT, Rule-Based, and Ensemble methods
- Achieved **69.2% accuracy** with weighted ensemble system, outperforming individual models
- Demonstrated that traditional ML (SVM: 68.43%) matched transformer performance (BERT: 68.16%) for keyword-driven tasks
- Conducted systematic hyperparameter tuning across 7 LSTM configurations and identified critical early stopping point for BERT (2 epochs optimal)
- Identified LSTM overparameterization issue (2.7M parameters for 8,764 samples) causing model collapse
- Created production-ready system with **50× faster inference** and **440× smaller memory footprint** than deep learning alternatives
- **Impact:** Demonstrated optimal model selection criteria balancing accuracy, efficiency, and interpretability for NLP tasks

**Technologies:** PyTorch, Hugging Face Transformers (BERT), scikit-learn, NLTK, TF-IDF, Python

---

### Comparative Analysis of AI Algorithms in Cybersecurity
**Research Paper | University of Michigan-Dearborn**  
*January 2024 – May 2024*

- Analyzed machine learning algorithms (Random Forest, SVM, Neural Networks) for threat detection efficacy and adversarial robustness
- Evaluated models across accuracy, precision, recall, and resilience to adversarial attacks (FGSM, PGD)
- Identified Random Forest as optimal balance between performance and adversarial robustness for intrusion detection
- Investigated adversarial training techniques to improve model resilience against evasion attacks
- **Impact:** Provided framework for selecting appropriate ML algorithms for security-critical applications

---

## Technical Skills

### AI/ML Frameworks & Tools
- **Deep Learning:** PyTorch, TensorFlow, Keras
- **ML Libraries:** scikit-learn, Pandas, NumPy, Matplotlib
- **NLP:** Hugging Face Transformers, NLTK, spaCy
- **Explainable AI:** SHAP, LIME, Captum (DeepLIFT, Integrated Gradients)
- **Causal Inference:** causal-learn (PC, GES algorithms)

### Programming Languages
- **Primary:** Python, Bash
- **Infrastructure as Code:** Terraform, Rego (OPA Policy Language)
- **Other:** Go, PowerShell, SQL

### Security Operations & Tools
- **SIEM:** Splunk, IBM QRadar, Elastic Stack
- **SOAR:** Palo Alto Cortex XSOAR, Splunk Phantom
- **EDR/XDR:** CrowdStrike Falcon, SentinelOne
- **UEBA:** Exabeam, Splunk UBA
- **Threat Intelligence:** MISP, ThreatConnect, STIX/TAXII
- **Vulnerability Management:** Qualys, Nessus, Rapid7

### Infrastructure & Cloud Security
- **Cloud Platforms:** AWS (EC2, S3, IAM, CloudTrail, GuardDuty)
- **Container Security:** Kubernetes Security, Docker
- **Policy as Code:** Open Policy Agent (OPA), Gatekeeper
- **CI/CD Security:** GitHub Actions, Jenkins, GitLab CI
- **IaC Security:** Terraform, CloudFormation

### Network & Endpoint Security
- **Firewalls:** Palo Alto Networks, Fortinet, Cisco ASA
- **Network Monitoring:** Wireshark, tcpdump, Zeek
- **Endpoint Protection:** Symantec, CrowdStrike, Carbon Black
- **Operating Systems:** Linux (RHEL, Ubuntu, CentOS), Windows Server

### Security Frameworks & Standards
- NIST Cybersecurity Framework
- CIS Benchmarks
- MITRE ATT&CK Framework
- ISO 27001
- PCI-DSS, HIPAA (compliance)

---

## Certifications

### Cloud & Kubernetes Security
- **GIAC Cloud Security Automation (GCSA)** - GIAC/SANS
- **AWS Certified Security – Specialty** - Amazon Web Services
- **Certified Kubernetes Administrator (CKA)** - Cloud Native Computing Foundation
- **Certified Kubernetes Security Specialist (CKS)** - Cloud Native Computing Foundation

---

## Publications & Presentations

### Research Papers
- **Sivakumar, B.**, Kayed, T., Luwaga, A., Jaimini, U. (2025). "Using Causal Inference and Explainable AI (XAI) to help improve Network Alert Prioritization/Classification in NIDS." *In preparation for submission.*

### Technical Presentations
- "PoliteMeter: Automated Politeness Detection System - A Comparative Study of ML Approaches" (December 2024)
- "Comparative Analysis of AI Algorithms in Cybersecurity" (May 2024)

---

## Professional Interests

### Research Areas
- Explainable AI for Security Applications
- Causal Inference in Cybersecurity
- Adversarial Machine Learning & Robustness
- AI-Powered Threat Detection and Response
- Trustworthy AI Systems

### Industry Focus
- AI/ML for Cybersecurity (AI-SecOps)
- Cloud Security & DevSecOps
- Security Automation & Orchestration
- Network Intrusion Detection
- Threat Intelligence & Hunting

---

## Leadership & Achievements

### Technical Leadership
- Led security engineering team of 4 members at Smarttech247, managing incident response and security operations
- Mentored 3+ junior security engineers, developing comprehensive training programs and knowledge transfer materials
- Reduced incident response time by 50% through SOAR automation and process optimization

### Automation & Efficiency
- Developed 15+ SOAR playbooks, automating repetitive security tasks and improving analyst productivity
- Created Python/Bash automation scripts saving 10+ hours per week in routine operations
- Implemented policy-as-code framework reducing manual security reviews by 60%

### Security Improvements
- Reduced false positive rate by 30% through SIEM tuning and correlation rule optimization
- Eliminated 200+ unused IAM roles with excessive permissions, reducing cloud attack surface
- Achieved 99.5% accuracy in NIDS alert classification through deep learning approach

---

## Additional Information

### Languages
- **English:** Fluent (Professional Working Proficiency)
- **Tamil:** Native

### Location
- **Current:**  Michigan, USA

---

## Contact Information

**Email:** brin2595@gmail.com  
**LinkedIn:** [linkedin.com/in/brindha-sivakumar](https://linkedin.com/in/brindha-sivakumar)  
**GitHub:** [github.com/yourusername](https://github.com/brindha-sivakumar)  
**Portfolio:** [yourusername.github.io](https://brindha-sivakumar.github.io/)  
**Phone:** 947-275-0417

---

