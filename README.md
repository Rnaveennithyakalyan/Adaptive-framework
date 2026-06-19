# Adaptive Framework Dataset for Quantum-Safe Real-Time Gross Settlement (RTGS)

## Abstract

This repository contains a synthetic dataset developed to evaluate an Adaptive Framework for Quantum-Safe Real-Time Gross Settlement (RTGS) environments. The dataset simulates financial transaction processing under varying Quantum Key Distribution (QKD) channel conditions by monitoring the Quantum Bit Error Rate (QBER). Based on the observed communication state, the framework dynamically switches between Hybrid Cryptography, Post-Quantum Cryptography (PQC), and Classical Fallback modes to balance security, availability, and computational efficiency. The dataset is intended for researchers working in quantum cybersecurity, financial technology, adaptive security architectures, and post-quantum cryptography.

---

## Research Motivation

Traditional RTGS systems are designed around static cryptographic mechanisms that cannot dynamically respond to fluctuating quantum communication channel conditions. Future financial infrastructures integrating Quantum Key Distribution require adaptive security mechanisms capable of maintaining confidentiality while ensuring uninterrupted settlement operations.

This dataset was developed to benchmark adaptive cryptographic switching strategies under multiple simulated communication scenarios.

---

# Dataset Information

| Property | Value |
|----------|-------|
| Dataset Name | Adaptive Framework Dataset |
| Version | 1.0.0 |
| Domain | Quantum Cybersecurity |
| Application | Quantum-Safe RTGS |
| Format | CSV |
| Language | English |
| License | CC BY 4.0 (Recommended) |
| Author | R. Naveen Nithya Kalyan |

---

# Dataset Features

| Feature | Description |
|----------|-------------|
| tx_id | Unique transaction identifier |
| qber | Simulated Quantum Bit Error Rate |
| ch_state | Communication channel state |
| mode | Adaptive cryptographic mode |
| lat_classical | Classical processing latency (ms) |
| lat_proposed | Proposed framework latency (ms) |
| overhead_ms | Additional latency introduced |
| overhead_pct | Percentage latency overhead |

---

# Channel States

- CLEAN
- NOISY
- ATTACKED
- DEGRADED

---

# Adaptive Modes

## Hybrid

Balances security and computational efficiency during nominal channel conditions.

## PQC-Only

Activated when potential attacks are detected to maximize cryptographic protection.

## Classical-Fallback

Maintains service availability when quantum communication becomes unstable.

---

# Repository Structure

```
Adaptive-Framework-Dataset/

adaptive_framework_dataset.csv

README.md

LICENSE

CITATION.cff

metadata.json

CHANGELOG.md
```

---

# Requirements

```
pip install pandas
```

---

# Loading the Dataset

```python
import pandas as pd

df = pd.read_csv("adaptive_framework_dataset.csv")

print(df.head())
```

---

# Potential Research Applications

- Quantum Cybersecurity
- Post-Quantum Cryptography
- Adaptive Security Systems
- Financial Security
- Real-Time Gross Settlement
- QKD Performance Benchmarking
- Secure Banking Infrastructure
- Intelligent Cryptographic Switching

---

# Citation

Please cite this dataset using the DOI assigned through Zenodo.
Repository updated for Zenodo DOI generation.

---

# Keywords

Quantum Computing

Quantum Cybersecurity

QKD

Post Quantum Cryptography

Adaptive Security

RTGS

Banking

Financial Systems

Cybersecurity

Benchmark Dataset
