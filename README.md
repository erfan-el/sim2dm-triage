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

The notebook [`triage_eventlog_preprocessing.ipynb`](https://github.com/erfan-el/sim2dm-triage/blob/main/triage_eventlog_preprocessing.ipynb) loads the synthetic triage event log and prepares labeled datasets for decision mining experiments. It includes:

* Loading and sorting the synthetic triage event log
* Deriving decision labels for four decision points (DP1–DP4) using trace-based rules:
  - DP1: first activity after A
  - DP2: labeling based on the C/D sequence before E (with forward/backward filling within each case)
  - DP3: first activity after E
  - DP4: first activity after G
* Encoding categorical attributes and DP labels into numeric features
* Exporting a fully labeled event log and separate datasets for training decision trees per DP
  (Each dataset is truncated to contain only events available before the corresponding decision point)

📦 **Output:** 
- [`labeled_triage_eventlog.csv`](https://github.com/erfan-el/sim2dm-triage/blob/main/labeled_triage_eventlog.csv)
- [`DP1_labeled_triage_eventlog.csv`](https://github.com/erfan-el/sim2dm-triage/blob/main/DP1_labeled_triage_eventlog.csv)
- [`DP2_labeled_triage_eventlog.csv`](https://github.com/erfan-el/sim2dm-triage/blob/main/DP2_labeled_triage_eventlog.csv)
- [`DP3_labeled_triage_eventlog.csv`](https://github.com/erfan-el/sim2dm-triage/blob/main/DP3_labeled_triage_eventlog.csv)
- [`DP4_labeled_triage_eventlog.csv`](https://github.com/erfan-el/sim2dm-triage/blob/main/DP4_labeled_triage_eventlog.csv)

---

## 🧠 3. Decision mining model training and rule extraction

The notebook [`model_training_for_DM__triage_process.ipynb`](https://github.com/erfan-el/sim2dm-triage/blob/main/model_training_for_DM__triage_process.ipynb) trains interpretable decision tree models for each decision point in the triage process using the labeled event logs. It focuses on learning and explaining routing decisions at DP1–DP4. It includes:

* Loading DP-specific labeled datasets (DP1–DP4)
* Training and evaluating decision tree classifiers using different feature sets
* Extracting human-readable decision rules from trained models
* Visualizing decision trees for each decision point

📦 **Output:** 
- [`decision_tree_DP1.png`](https://github.com/erfan-el/sim2dm-triage/blob/main/decision_tree_DP1.png)
- [`decision_tree_DP2.png`](https://github.com/erfan-el/sim2dm-triage/blob/main/decision_tree_DP2.png)
- [`decision_tree_DP3.png`](https://github.com/erfan-el/sim2dm-triage/blob/main/decision_tree_DP3.png)
- [`decision_tree_DP4.png` ](https://github.com/erfan-el/sim2dm-triage/blob/main/decision_tree_DP4.png) 
    *(visual representations of the learned decision rules for each decision point)*

