# Applied Search Intelligence: Content Refresh Opportunity Scoring
### Capstone Research & Machine Learning Pipeline

[![GitHub Pages Deployment](https://img.shields.io/badge/Deployed_Paper-Live_on_GitHub_Pages-blue?style=for-the-badge&logo=github)](https://dhanish0711.github.io/FlyRank-Machine-Learning-Internship/)
[![Open In Colab](https://img.shields.io/badge/Open_In_Colab-Capstone_Notebook-orange?style=for-the-badge&logo=googlecolab)](https://colab.research.google.com/github/dhanish0711/FlyRank-Machine-Learning-Internship/blob/main/work/notebooks/capstone.ipynb)
[![Python 3.10+](https://img.shields.io/badge/Python-3.10+-brightgreen?style=for-the-badge&logo=python)](https://python.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)](LICENSE)

> **Deployed Research Paper:** [https://dhanish0711.github.io/FlyRank-Machine-Learning-Internship/](https://dhanish0711.github.io/FlyRank-Machine-Learning-Internship/)  
> **Author:** Dhanish Ladwani  
> **Track:** FlyRank Applied Machine Learning Internship

---

## 📌 Executive Summary

Enterprise content libraries experience organic search traffic decay as articles age and search engine result pages (SERPs) evolve, but editorial review bandwidth is strictly capacity-constrained (20–50 articles per weekly sprint).

Using an anonymized **30,000-page production search dataset across 32 enterprise clients** from the FlyRank search intelligence warehouse, we built and benchmarked a machine learning ranking system to prioritize content refresh opportunities.

### Key Results
- **Generalization Integrity:** Evaluated under an honest, leak-free **Client-Holdout Grouped Validation Design** (`GroupShuffleSplit` on `client_id`, 24 train / 8 test clients).
- **Benchmark Winner:** **Gradient Boosting** achieved **Precision@50 = 0.740** on blind test client domains, outperforming the heuristic hand rule (0.600) by **+14.0 percentage points** and well above the test base rate (0.517).
- **Financial ROI:** Saves an estimated **$1,400/week per client** in avoided wasted rewrites on healthy evergreen articles.
- **Operational Product:** Model probabilities are operationalized into 4 actionable editorial archetypes with transparent reason codes and strict no-go automation boundaries.

---

## 📊 Benchmark Comparison Table (Client-Holdout Evaluation)

| Model / Method | Precision@20 | Precision@50 | ROC-AUC | Avg Precision | Test Base Rate |
|---|:---:|:---:|:---:|:---:|:---:|
| **Baseline Hand Rule** | 0.500 | 0.600 | 0.548 | 0.538 | 0.517 |
| **Logistic Regression** | 0.650 | 0.660 | 0.540 | 0.539 | 0.517 |
| **Decision Tree (depth=4)** | 0.650 | 0.560 | 0.578 | 0.566 | 0.517 |
| **Random Forest** | 0.550 | 0.540 | 0.598 | 0.593 | 0.517 |
| **Gradient Boosting (Winner)** | **0.800** | **0.740** | **0.612** | **0.612** | 0.517 |

---

## 🛠️ Repository Architecture

```text
├── data/
│   └── raw/content_refresh_anonymized.csv   # 30,000-page pseudonymized warehouse snapshot
├── docs/
│   ├── index.html                           # Live Deployed Research Paper (with Interactive Calculator)
│   └── figures/                             # High-resolution benchmark figures
├── submission/
│   └── paper_url.txt                        # Deployed paper URL receipt (Mandatory submission)
├── work/
│   ├── figures/                             # Exported chart assets
│   ├── notebooks/
│   │   ├── w01_research_question.ipynb      # ML-02: Framing & Provisional Lane
│   │   ├── w02_ml_task_framing.ipynb        # ML-03: Ranking Task Definition
│   │   ├── w03_data_contract.ipynb          # ML-04: Data Contract & Leakage Checks
│   │   ├── w04_baseline_score.ipynb         # ML-07: Baseline Action Score & Signal Audit
│   │   ├── w05_model.ipynb                  # ML-08: Capstone Modeling Lane Benchmark
│   │   ├── w06_validation_audit.ipynb       # ML-09: Validation & Claim Audit
│   │   ├── w07_action_playbook.ipynb        # ML-10: Content Action Playbook
│   │   └── capstone.ipynb                   # ML-11 / ML-12: Full Executed Capstone
│   ├── outputs/                             # Exported JSON metric receipts & action queue
│   └── storytelling.md                      # ML-12: 5-min demo outline & shareable cuts
```

---

## 🚀 Quickstart & Reproducibility

### 1. Clone & Environment Setup
```bash
git clone https://github.com/dhanish0711/FlyRank-Machine-Learning-Internship.git
cd FlyRank-Machine-Learning-Internship
pip install -r requirements.txt
```

### 2. Run All Pipelines & Re-generate Receipts
```bash
# Execute Capstone Pipeline
jupyter nbconvert --to notebook --execute work/notebooks/capstone.ipynb
```

---

## 📄 Acknowledgments & Data Credit

This research was developed as part of the **FlyRank Applied Search Intelligence Internship**.  
Built on the **[FlyRank ML Internship Dataset](https://flyrank.ai/)**.
