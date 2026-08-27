# ML-12 — Tell the Story: Showcase Outline & Shareable Cuts

**Author:** Dhanish Ladwani  
**Track:** Machine Learning — Capstone  
**Repository:** [dhanish0711/FlyRank-Machine-Learning-Internship](https://github.com/dhanish0711/FlyRank-Machine-Learning-Internship)  
**Deployed Paper:** [https://dhanish0711.github.io/FlyRank-Machine-Learning-Internship/](https://dhanish0711.github.io/FlyRank-Machine-Learning-Internship/)  

---

## 1. 5-Minute Technical Showcase Demo Outline

*Target Audience: ML Engineers, Hiring Managers, SEO Operations Directors*

### Minute 1: The Operational Problem & Asymmetric Error Costs (0:00 – 1:00)
* **The Problem:** Enterprise digital libraries contain thousands of articles. Over a 90-day window, 54.2% of pages experience organic traffic decay.
* **The Operational Bottleneck:** Editorial teams have finite bandwidth (20–50 articles per weekly sprint).
* **The Heuristic Failure:** Static rules (e.g. "refresh articles older than 6 months") misclassify healthy evergreen content 38.9% of the time, wasting $150–$300 per unnecessary rewrite while missing high-traffic decaying URLs.

### Minute 2: Data River, Grain & Leakage Hygiene (1:00 – 2:00)
* **The Dataset:** 30,000 production search pages across 32 enterprise clients from the FlyRank search intelligence warehouse.
* **The Contract Grain:** One row = One pseudonymized content item (`content_id`) per client (`client_id`) over 90 days.
* **Leakage Defense:** Show that target-derived features (`trend_pct`) and existing heuristic flags (`health_score`) were strictly excluded from input matrices.

### Minute 3: Grouped Client-Holdout Validation Design (2:00 – 3:00)
* **The Trap:** Random row-wise splits allow models to memorize domain-specific baseline CTRs and domain authority, creating artificially inflated metrics (Precision@50 = 0.820).
* **The Honest Solution:** `GroupShuffleSplit` on `client_id` (24 train clients / 8 blind test clients), reserving entire client domains to evaluate genuine out-of-domain generalization.

### Minute 4: Model Benchmark & Non-Linear Signals (3:00 – 4:00)
* **The Benchmark:** Gradient Boosting achieves **Precision@50 = 0.740** on unseen client domains (+14.0 points over the 0.600 baseline rule, and +22.3 points over the 0.517 base rate).
* **Feature Interactions:** Decisions are driven primarily by non-linear interactions between 90-day search impressions (42.2%) and content age (22.1%).

### Minute 5: Content Action Playbook & Live Research Paper (4:00 – 5:00)
* **The Product:** Model outputs convert directly into 4 actionable archetypes (`comprehensive_content_refresh`, `title_meta_rewrite`, `engagement_ux_optimization`, `performance_monitoring`) with transparent reason codes.
* **Governance:** Strict no-go automation rules (no automated 410 deletions, no unreviewed AI text generation) and drift retrain triggers.
* **Live Paper:** Walk through the deployed publication at `https://dhanish0711.github.io/FlyRank-Machine-Learning-Internship/`.

---

## 2. Shareable Cut 1: Methodology Social Post (LinkedIn / X / Portfolio)

> **How do you know which of your 10,000 published articles to update first?** 📈
>
> In enterprise SEO, standard heuristic rules (e.g. *"refresh everything older than 6 months"*) often fail because they misdiagnose stable evergreen articles, wasting hundreds of editorial hours.
>
> Using 30,000 production pages across 32 enterprise client domains from the FlyRank search intelligence warehouse, I built and audited a machine learning prioritization system.
>
> 🔍 **Key findings from our client-holdout research:**
> • **The Generalization Trap:** Naive random train/test splits inflated performance to 0.820 by memorizing client domain authority. Reserving whole client domains via `GroupShuffleSplit` provided an honest Precision@50 of **0.740**.
> • **The Model:** Gradient Boosting outperformed hand rules (0.600) by **+14.0 percentage points**, driven by non-linear interactions between impression demand and staleness.
> • **Operational Playbook:** Converted probabilities into 4 human-in-the-loop action archetypes with transparent reason codes and strict no-go automation boundaries.
>
> 📄 Read the full deployed research paper: https://dhanish0711.github.io/FlyRank-Machine-Learning-Internship/  
> 💻 Reproducible code & data contract: https://github.com/dhanish0711/FlyRank-Machine-Learning-Internship  
>
> #MachineLearning #DataScience #AppliedML #SEO #SearchIntelligence #Python

---

## 3. Shareable Cut 2: 3-Sentence Employer-Facing Summary

1. **What I Built:** Developed an end-to-end machine learning content refresh prioritization engine that maps search telemetry into ranked editorial queues with human-readable reason codes.
2. **On What Data:** Evaluated across 30,000 production search pages from 32 enterprise clients using an honest, leak-free client-holdout grouped validation design (`GroupShuffleSplit` on `client_id`).
3. **What It Showed:** Gradient Boosting achieved a validated **Precision@50 of 0.740** on unseen client domains—outperforming heuristic baseline rules by +14.0 percentage points—and was deployed as an interactive public research paper with strict reproducibility guarantees.

---

## 4. Submission Checklist (ML-12)
- [x] Paper's Abstract and Introduction tie findings directly to the FlyRank content decay problem in public-safe language.
- [x] 5-minute technical demo outline written and committed.
- [x] Methodology social post cut written and formatted for immediate sharing.
- [x] 3-sentence employer-facing summary drafted and committed.
- [x] Deployed research paper live at https://dhanish0711.github.io/FlyRank-Machine-Learning-Internship/
