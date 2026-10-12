---
title: "ThreatSearch: Domain-Adapted Information Retrieval over NVD and MITRE ATT&CK"
excerpt: "A full IR stack over 97K CVEs and 691 ATT&CK techniques, combining exact and semantic retrieval with security-aware NLP <br>
- Task: ranked retrieval of vulnerability advisories by query relevance across NVD and ATT&CK <br>

* Models: BM25, TF-IDF, LSA (TruncatedSVD, k=300), LDA topic modeling <br>
* Stack: Python, scikit-learn, gensim, NLTK, NumPy/SciPy, Matplotlib, Colab"
collection: portfolio
---

## AI Focus Area

NLP | Information Retrieval | Semantic Search | Topic Modeling | Security Domain Adaptation

---

## Overview

Security analysts searching vulnerability databases face a vocabulary mismatch problem: a CVE describing a use-after-free will not surface under a query for "memory corruption" using standard keyword search. ThreatSearch is a domain-adapted retrieval system built from scratch over the NVD CVE feeds (2021–2026, ~97K documents) and the MITRE ATT&CK STIX bundle (691 techniques). It combines exact and semantic retrieval with ATT&CK-aware query expansion, so a search for "credential dumping" automatically incorporates related technique IDs and the CVEs historically associated with them.

---

## Technical Implementation

- Ingested NVD JSON feeds and ATT&CK STIX into a sharded corpus with a pre-pass that preserves CVE/CWE/T-IDs as atomic tokens, bypassing the stemmer for structured identifiers; expanded security acronyms inline (RCE → remotecodeexecution)
- Built a two-pass inverted index over 11 corpus shards (117,795 terms, 2.4M postings), followed by an external k-way merge sort producing a single `index_merged.txt` (57.6 MB); memory bounded to one line per shard throughout
- Implemented BM25 (k1=1.5, b=0.75) and TF-IDF scoring with a 1.3× source weight boost for ATT&CK documents; posting lists loaded lazily and cached per session
- Built ATT&CK query expansion by computing keyword overlap between each CVE description and each technique's text (min 3 shared stemmed tokens), producing a technique→CVE map of 8.3M pairs across 691 techniques; injected technique IDs at 0.6× weight and CVE IDs at 0.4× to preserve query intent
- Implemented Boolean AND/OR/NOT with a recursive descent parser and AST evaluator; Boolean filter runs as a hard pre-filter and the ranked scorer re-scores only the matching candidate set
- Built an LSA index using a sparse TF-IDF matrix (117,795 × 96,670) compressed to 300 latent dimensions via TruncatedSVD; query scoring is a single L2-normalised dot product against the document matrix with fixed memory footprint at runtime
- Trained LDA (20 topics, gensim) over 233K documents using disk-streamed `MmCorpus` to avoid in-memory corpus blowup; diagnosed and fixed a silent batch inference bug caused by `per_word_topics=True`; coherence evaluation sampled to 20K documents to avoid hang on full corpus

---

## Key Results

- LSA surfaces synonymous CVEs that BM25 misses entirely — "memory corruption" retrieves use-after-free, heap spray, and dangling pointer CVEs with no vocabulary overlap
- ATT&CK expansion adds meaningful recall depth: "credential dumping lsass" injects T1003/T1003.001 and their associated CVEs, including records that never use the query phrase
- LSA variance retained at 300 dimensions: 33–37% across corpus sizes
- LDA C_v coherence: 0.57 — topics correspond to recognisable vulnerability classes (XSS, memory safety, kernel bugs, authentication bypass)

---

## Skills Demonstrated

**AI/ML**
- Sparse matrix decomposition and semantic similarity at scale (LSA/SVD)
- Topic model design with corpus-specific NLP — separate stemming strategy for retrieval vs. topic readability
- Retrieval architecture: inverted index, ranked scoring, Boolean pre-filtering, hybrid exact/semantic pipelines

**Cybersecurity Domain**
- NVD CVE and MITRE ATT&CK data pipelines, STIX bundle parsing
- Security-aware NLP: ID preservation, domain stopword design, acronym expansion
- ATT&CK kill-chain alignment via tactic×topic heatmap visualization

**Systems**
- External merge sort for index files exceeding RAM; streaming corpus serialization for LDA at scale
- Retry and HTTP Range resume for large feed downloads under unstable connections
- Reproducing results across Colab and Windows environments
