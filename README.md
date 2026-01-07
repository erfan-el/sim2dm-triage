# 🏥 sim2dm-triage: Generating a Synthetic Event Log and Applying Decision Mining for the Triage Process

This repository provides a simulated healthcare triage event log and supports decision modeling, process mining (PM), and decision mining (DM) experiments.

---

## 📄 1. Synthetic Event Log Generation

The notebook [`generate_synthetic_triage_eventlog.ipynb`](https://github.com/erfan-el/sim2dm-triage/blob/main/generate_synthetic_triage_eventlog.ipynb) generates a synthetic event log based on a triage process involving patient assessment, treatment routing, and discharge or escalation. It includes:

* Definition of a triage process with nine activities.
* Simulation of patient attributes (heart rate, oxygen saturation, blood pressure, age, consciousness level)
* Computation of a Patient Health Indicator (PHI) with four severity levels (Stable, Deteriorating, Critical, Life-Threatening)
* Rule-based routing logic with four decision points (DP1–DP4), including loops and escalation paths
* Event creation with activity labels, timestamps, and event attributes.
* Variant extraction and frequency analysis.

📦 **Output:** [`synthetic_triage_eventlog.csv`](https://github.com/erfan-el/sim2dm-triage/blob/main/synthetic_triage_eventlog.csv)

---

## 🏷️ 2. Event log preprocessing and decision point labeling

The notebook [`triage_eventlog_preprocessing.ipynb`](https://github.com/erfan-el/sim2dm-triage/blob/main/triage_eventlog_preprocessing.ipynb) enhances the synthetic event log by explicitly identifying and labeling decision points in the triage process. In particular, it focuses on four decision points (DP1–DP4) derived from the process structure and routing logic. It features:

* Per-case activity sequence analysis
* Rule-based labeling for DPs
* Export of the enriched log for further analysis (DM)

📦 **Output:** [`labeled_triage_eventlog.csv`](https://github.com/erfan-el/sim2dm-triage/blob/main/labeled_triage_eventlog.csv)

---

