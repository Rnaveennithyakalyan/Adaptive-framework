# Adaptive framework

This repository contains the dataset for an Adaptive Framework designed for quantum-safe Real-Time Gross Settlement (RTGS) environments. The dataset simulates real-time transaction processing across varying network channel conditions, demonstrating how the framework dynamically adapts its cryptographic security modes based on the monitored Quantum Bit Error Rate (QBER).

## Dataset Overview

The dataset tracks transactional performance, security modes, and processing overhead across four distinct channel states. 

### Feature Descriptions

* **`tx_id`**: A unique incremental identifier assigned to each transaction sequence.
* **`qber`**: The simulated Quantum Bit Error Rate. Higher values signify increased channel noise or active interception attempts.
* **`ch_state`**: The classified state of the communication channel determined by network telemetry and QBER thresholds:
    * `CLEAN`
    * `NOISY`
    * `ATTACKED`
    * `DEGRADED`
* **`mode`**: The adapted cryptographic mode triggered by the system state:
    * `Hybrid`: Active during standard or slightly noisy environments (`CLEAN`/`NOISY`) to balance post-quantum security with baseline operations.
    * `PQC-Only`: Triggered during high-risk conditions (`ATTACKED`) to isolate traffic entirely using Post-Quantum Cryptography.
    * `Classical-Fallback`: Deployed during severe network degradation (`DEGRADED`) to keep settlement systems operational by reverting to lightweight, optimized classical primitives when quantum key distribution is unviable.
* **`lat_classical`**: The baseline latency observed when using standard classical cryptographic routines (measured in milliseconds).
* **`lat_proposed`**: The total latency observed under the active mode of the proposed adaptive framework (measured in milliseconds).
* **`overhead_ms`**: The raw computational and network latency overhead introduced by the adaptive logic, calculated as:
    $$overhead\_ms = lat\_proposed - lat\_classical$$
* **`overhead_pct`**: The relative percentage increase or decrease in processing time compared to the classical baseline.

---

## Technical Architecture Mapping

The transactional logs reveal three key performance patterns hardcoded into the adaptive logic:

1.  **Standard Performance Line (`CLEAN` / `NOISY`)**: Uses the `Hybrid` cryptographic mode. It maintains a steady processing latency overhead to guarantee structural safety under nominal operating bounds.
2.  **Attack Defiance Mode (`ATTACKED`)**: Shifts directly to `PQC-Only` or isolated `Hybrid` security structures to prioritize absolute data integrity at the expense of computational overhead.
3.  **High-Availability Fallback (`DEGRADED`)**: When QBER scales beyond stable operational thresholds, the framework drops into a `Classical-Fallback` state. This minimizes performance penalties to ensure continuous financial clearing, occasionally resulting in negative relative overhead profiles (faster than complex hybrid processing).

---

## Quick Start for Data Analysis

To analyze the file locally using Python, verify that you have `pandas` installed:

```bash
pip install pandas
