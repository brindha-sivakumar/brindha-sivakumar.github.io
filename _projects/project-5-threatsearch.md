---
title: " ThreatSearch  [In Progress]"
excerpt: "Unified Cyber Threat Intelligence Search Engine <br>"

collection: portfolio
---

## AI Focus Area
Information Retrieval | CTI | BM25 | MITRE ATT&CK | NER | FAISS | Streamlit

## Overview
Threat analysts investigating incidents must manually search MITRE ATT&CK, CISA advisories, the NVD, and vendor reports separately — each with different interfaces and vocabulary. ThreatSearch unifies these sources into a single ranked search engine purpose-built for cyber threat intelligence (CTI), combining classical information retrieval with dense vector search and security-domain NLP.

## Technical Implementation
- Ingesting MITRE ATT&CK STIX bundles, CISA KEV advisories, and a NVD subset into a unified document store
- Extending a custom inverted index with TF-IDF weights and BM25 scoring, built on top of a prior IR course checkpoint
- Security-aware preprocessing: CVE ID preservation, protected compound terms (e.g. 'lateral movement'), security stopwords
- Named entity extraction for CVE IDs, MITRE TTP codes, and APT group names using rule-based and transformer NER
- Query expansion dictionary mapping security synonyms (e.g. 'ransomware' → 'encryption', 'exfiltration')
- Dense retrieval layer: sentence-transformer embeddings indexed with FAISS; hybrid fusion using Reciprocal Rank Fusion (RRF)
- Evaluation framework: 50-query test set with manual relevance judgments; NDCG@10 and MAP metrics via pytrec_eval
- Streamlit UI: search box, ranked results with entity highlights, source badges (MITRE / CISA / NVD), expandable previews



## Tech Stack
Python · BM25 · FAISS · Sentence Transformers · spaCy · Streamlit · MITRE ATT&CK STIX · CISA KEV API · NVD API · pytrec_eval