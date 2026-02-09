# 5GCoreSec: 5G Core Network Intrusion Detection Dataset
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**5GCoreSec** is a large-scale labeled dataset of **5G core (user-plane) traffic** designed for machine-learning-based intrusion detection research. It is collected from a reproducible 5G core testbed built with **Open5GS** and **UERANSIM**, including network slicing for Internet and IoT services.

> If you use this dataset in your research, please cite the paper(s) listed below.

---

## Table of Contents
- [Related Publications](#related-publications)
- [Dataset Description](#dataset-description)
- [Dataset Statistics](#dataset-statistics)
- [Getting Started](#getting-started)
- [File Structure](#file-structure)
- [Data Dictionary](#data-dictionary)
- [How to Cite](#how-to-cite)
- [License](#license)

---

## Related Publications

**Primary publication (dataset paper):**
1. **Sheikhi, S. (2026).** *5GCoreSec: A Large-Scale GTP-U Traffic Dataset for Machine Learning-Based Intrusion Detection in 5G Networks.* In Proceedings of **ACM KDD 2026**.

---

## Dataset Description

The goal of 5GCoreSec is to provide a **realistic, labeled dataset** for intrusion detection in modern 5G core networks, including the **extreme class imbalance** found in operational settings.

**Key characteristics**
- **Testbed:** Open5GS (core) + UERANSIM (UE/RAN), with **network slicing** for Internet (eMBB) and IoT (mMTC) services.
- **Traffic & labeling:** benign traffic plus **8 attack types**:  
  `DoS_MQTT`, `DDoS`, `Eavesdropping`, `MITM`, `SQL Injection`, `Brute Force`, `Unauthorized Data Access`, `Device Spoofing` (plus `benign`).
- **Splits:** predefined **train/test splits** (90/10) designed to preserve class proportions.
- **Features:** **28 extracted features** derived from network-observable header/time fields (exported from packet captures using TShark-based extraction).

---

## File Structure

The data is provided in multiple CSV files:
* `Train_subset_1.csv` & `Train_subset_2.csv`: These contain training data and can be used separately or combined into a larger training set.
* `Test_Data.csv`: A unified test set containing all traffic types for evaluating the final model.

The repository should be structured as follows:
```
.
├── data/
│   ├── training_data.csv
│   └── testing_data.csv
├── class_distribution_train_test_log.png
├── class_distribution_train_test_pct.png
│   
├── .gitignore
├── LICENSE
└── README.md
---


## Dataset Statistics

### Splits
- **Train shape:** `(1,753,454, 29)`
- **Test shape:** `(194,829, 29)`
- **Label column:** `attack`
- **Train memory:** `623.69 MB`
- **Test memory:** `69.31 MB`

### Classes (9 total)
`benign`, `DoS_MQTT`, `DDoS`, `Eavesdropping`, `MITM`, `SQL Injection`, `Brute Force`, `Unauthorized Data Access`, `Device Spoofing`

### Label / Class Distribution (Train vs Test)

| Class | Train count | Train % | Test count | Test % |
| --- | ---:| ---:| ---:| ---:|
| benign | 1332625 | 76.000000 | 148070 | 76.000000 |
| DoS_MQTT | 250514 | 14.286900 | 27835 | 14.286900 |
| DDoS | 165070 | 9.413990 | 18341 | 9.413900 |
| Eavesdropping | 3525 | 0.201032 | 392 | 0.201202 |
| MITM | 677 | 0.038610 | 75 | 0.038495 |
| SQL Injection | 475 | 0.027089 | 53 | 0.027203 |
| Brute Force | 291 | 0.016596 | 32 | 0.016425 |
| Unauthorized Data Access | 207 | 0.011805 | 23 | 0.011805 |
| Device Spoofing | 70 | 0.003992 | 8 | 0.004106 |

- **Train imbalance ratio (majority/minority):** `19037.50`
- **Test imbalance ratio (majority/minority):** `18508.75`

### Missing Values (important note)
Many fields are **protocol-dependent** (e.g., UDP fields are missing for TCP packets, HTTP fields missing for non-HTTP traffic). High missingness in some columns is expected and should be handled during preprocessing.

---

## Getting Started

### Prerequisites
- Python 3.8+
- `pandas`, `numpy`

### Example Usage

```python
import pandas as pd

# Load dataset splits
training_data = pd.read_csv("training_data.csv")
testing_data  = pd.read_csv("testing_data.csv")

print("Train shape:", training_data.shape)
print("Test shape:", testing_data.shape)

# Basic sanity checks
print("Label column: attack")
print("Train class counts:\n", training_data["attack"].value_counts())
print("Test class counts:\n", testing_data["attack"].value_counts())
