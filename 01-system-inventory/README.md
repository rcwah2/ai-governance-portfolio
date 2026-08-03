# Artifact 1: AI System Inventory

Regulators start with "know what you have." Most companies can't answer that question with any precision — this artifact is practice at answering it precisely, one system at a time, with reasoning that holds up under questioning rather than a label filled into a template.

## System 1: Bank Credit-Scoring Model (hypothetical, global bank)

| Field | Entry |
|---|---|
| **Purpose** | Predicts likelihood of default; the prediction drives loan approval/denial, interest rate, and credit limit decisions. |
| **Model Type** | Gradient-boosted tree ensemble (e.g., XGBoost) paired with a post-hoc explainability layer (e.g., SHAP). Model type directly determines whether human oversight can be performed effectively — a loan officer can't meaningfully review a denial from a model they can't interpret. SHAP shows which factors (income, credit utilization, payment history) contributed to a denial, letting the officer judge whether it was justified. A scorecard or single decision tree would satisfy the oversight requirement natively, at some cost to predictive accuracy. |
| **Risk Tier** | High. A credit score affects a consumer's employment, housing, and loan terms. The burden of proving the score is wrong lies with the consumer, not the bank. A model that automates scoring could introduce systemic bias affecting a group of consumers — and even with periodic human auditing, consumers are still impacted between audits. |
| **Jurisdiction** | Multi-jurisdictional, applicant-location-triggered. Jurisdiction follows where the affected applicant is located, not where the bank is headquartered or operates — the same principle EU regulators used against Clearview AI's "no EU establishment" defense. |
| **Human Oversight** | The loan officer must review all denials before notification to the consumer, documenting why the denial was, or wasn't, justified — this addresses the burden-of-proof problem directly. Separately, a compliance team monitors aggregate scoring trends and periodically samples decisions across score ranges to catch systemic bias. |
| **Data Sources** | Core sources: credit bureau data, employment/income data, internal banking data. Other data sources carry distinct risks: accuracy and fairness concerns for rent, utility, and telecom payment history; discrimination risk for zip code and demographic data; and privacy concerns for behavioral/digital data. Zip code, for example, is a proxy for the protected characteristic of race — though exclusion alone doesn't guarantee fairness, since other included variables like income or employment data can be correlated with zip code and reconstruct the same discriminatory signal indirectly. The compliance team runs demographic parity and equalized-odds testing on model outputs, measured as a selection-rate ratio between groups (Group B's approval rate divided by Group A's): ratio ≥ 0.90 → flag for next scheduled retraining cycle; 0.80–0.89 → escalate to committee; below 0.80 → immediate pull from production. |

**Why these thresholds:** the four-fifths rule in US fair-lending law treats a selection-rate ratio below 0.80 as a legal trigger for disparate-impact scrutiny. The tiers above build in a deliberate margin — routine monitoring (0.90+) doesn't wait until the model is already at the legal line, and committee escalation is reserved for the genuinely ambiguous, volatile zone (0.80–0.89) where a fixed rule shouldn't make the call alone.

---

*Systems 2–8 in progress. See the [main portfolio README](../README.md) for the full artifact roadmap. Full reasoning behind each field is on [Substack](https://rwahai.substack.com).*
