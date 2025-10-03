# 🏥 sim2dm-triage: Generating a Synthetic Event Log and Applying Decision Mining for the Triage Process

This repository provides a simulated healthcare triage event log and supports decision modeling, process mining (PM), and decision mining (DM) experiments.

---

## 📄 Synthetic Event Log Generation

The notebook [`generate_synthetic_triage_eventlog.ipynb`](https://github.com/erfan-el/sim2dm-triage/blob/main/generate_synthetic_triage_eventlog.ipynb) generates a synthetic event log based on a triage process involving patient assessment, treatment routing, and discharge or escalation. It includes:

* Simulated patient vitals (HR, SpO₂, BP, age) and PHI (Patient Health Indicator) classification
* Rule-based routing logic simulating care paths (e.g., CPR loop, diagnostics, ICU transfer)
* Event creation with activity labels, timestamps, and event attributes
* Variant extraction and frequency analysis

📦 **Output:** [`synthetic_triage_eventlog.csv`](https://github.com/erfan-el/sim2dm-triage/blob/main/synthetic_triage_eventlog.csv)

---

## 🏷️ Decision Point Labeling

The notebook [`triage_eventlog_preprocessing.ipynb`](https://github.com/erfan-el/sim2dm-triage/blob/main/triage_eventlog_preprocessing.ipynb) enhances the generated log by labeling decision points (`DP1–DP4`) using activity sequence logic and behavioral patterns. It features:

* Per-case activity sequence analysis
* Rule-based labeling for DPs
* Export of the enriched log for further analysis (DM)

📦 **Output:** [`labeled_triage_eventlog.csv`](https://github.com/erfan-el/sim2dm-triage/blob/main/labeled_triage_eventlog.csv)

---
