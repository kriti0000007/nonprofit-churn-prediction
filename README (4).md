# Nonprofit SaaS Churn Prediction

Predictive churn modeling for a B2B SaaS platform serving nonprofit organizations — combining behavioral data analysis, logistic regression, risk segmentation, and a lifecycle intervention playbook.

---

## Overview

Subscription churn in the nonprofit SaaS sector is rarely sudden. Organizations exhibit measurable behavioral warning signs weeks before canceling — declining platform engagement, shrinking feature adoption, and payment friction. This project identifies those signals, quantifies their predictive power, and maps them to targeted marketing interventions.

**Model performance: ROC-AUC 0.981**

---

## Key Findings

The model identified three leading churn signals, in order of predictive strength:

1. **Missed payments** — the single strongest predictor; even one missed payment significantly elevates churn probability
2. **Login frequency** — declining logins are a reliable early warning signal, preceding cancellation by weeks
3. **Feature adoption breadth** — organizations using only 1–2 platform features rarely renew

---

## Dataset

| Attribute | Detail |
|---|---|
| Records | 300 nonprofit organizations |
| Features | Login frequency, features used, missed payments, support tickets, org size, tenure |
| Target variable | Churned (1) / Active (0) |
| Churn rate | ~10% (realistic for B2B SaaS) |

---

## Methodology

| Stage | Approach |
|---|---|
| Exploratory analysis | Distribution and churn rate analysis across all behavioral features |
| Modeling | Logistic regression with StandardScaler normalization, 80/20 train-test split |
| Evaluation | Confusion matrix, precision/recall, F1, ROC-AUC |
| Segmentation | Churn score thresholds defining Low / Medium / High risk tiers |
| Output | Scored customer list + intervention playbook per risk tier |

---

## Risk Segmentation & Intervention Playbook

| Tier | Score Range | Profile | Campaign |
|---|---|---|---|
| Low risk | 0.00 – 0.40 | Engaged, multi-feature users, consistent payment history | Loyalty and expansion — upsell, testimonials, early feature access |
| Medium risk | 0.40 – 0.70 | Declining logins, limited feature adoption, no payment issues yet | Re-engagement — feature adoption email series, webinar invite, CS check-in |
| High risk | 0.70 – 1.00 | Near-inactive, missed payments, minimal platform usage | Urgent win-back — personal outreach, discount or payment plan, exit survey |

Campaigns are designed to trigger automatically when a customer's churn score crosses each tier threshold.

---

## Output Files

| File | Description |
|---|---|
| `nonprofit_churn_prediction.ipynb` | End-to-end analysis notebook |
| `outputs/eda_charts.png` | Behavioral patterns by churn status |
| `outputs/model_evaluation.png` | Confusion matrix and ROC curve |
| `outputs/feature_importance.png` | Model coefficients by feature |
| `outputs/risk_segmentation.png` | Score distribution and tier breakdown |
| `outputs/scored_customers.csv` | Full scored dataset, ready for CRM upload |

---

## Tech Stack

`Python` · `pandas` · `numpy` · `scikit-learn` · `matplotlib` · `seaborn`

---

**Kriti Singhal** · Marketing Analytics · [linkedin.com/in/singhal-kriti](https://linkedin.com/in/singhal-kriti/)
