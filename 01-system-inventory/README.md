# Artifact 1: AI System Inventory

Regulators start with "know what you have." Most companies can't answer that question with any precision — this artifact is practice at answering it precisely, one system at a time, with reasoning that holds up under questioning rather than a label filled into a template.

## System 1: Bank Credit-Scoring Model (hypothetical, global bank)

| Field | Entry |
|---|---|
| **Purpose** | Predicts likelihood of default; the prediction drives loan approval/denial, interest rate, and credit limit decisions. |
| **Model Type** | Gradient-boosted tree ensemble (e.g., XGBoost) paired with a post-hoc explainability layer (e.g., SHAP) to render individual predictions interpretable for mandatory human review. A logistic-regression scorecard or single decision tree would satisfy the same oversight requirement natively, at some cost to predictive accuracy — a deliberate trade-off, not a default. |
| **Risk Tier** | High. Credit decisions gate access to essential life opportunities (employment, housing, loan rates). The burden of contesting an error sits on the individual, not the bank. Automation converts an isolated human misjudgment into a systematic, consistent error applied at scale. |
| **Jurisdiction** | Multi-jurisdictional, applicant-location-triggered. Regulatory reach attaches to where the affected applicant is located, not where the bank is headquartered or operates — the same principle EU regulators used to reject Clearview AI's "we have no EU establishment" defense. |
| **Human Oversight** | Every automated denial is routed to a human loan officer for mandatory review before the applicant is notified. Separately, a compliance team monitors aggregate scoring trends and periodically samples approved/denied decisions across score ranges to detect systemic bias or drift. |
| **Data Sources** | Credit bureau data, internal transaction data, employment/income data. Zip code and other known proxy variables excluded by policy — exclusion alone doesn't guarantee fairness, since correlated variables can reconstruct the same signal indirectly (proxy discrimination). Compliance team runs demographic parity and equalized-odds testing on model *outputs*, measured as a selection-rate ratio between groups: ratio ≥ 0.90 → flag for next scheduled retraining cycle; 0.80–0.89 → escalate to committee for judgment call; below 0.80 → immediate pull from production. |

**Why these thresholds:** the four-fifths rule in US fair-lending law treats a selection-rate ratio below 0.80 as a legal trigger for disparate-impact scrutiny. The tiers above are built with a deliberate margin — routine monitoring (0.90+) doesn't wait until the model is already at the legal line, and committee escalation is reserved for the genuinely ambiguous zone (0.80–0.89) where a fixed rule shouldn't make the call alone.

---

*Systems 2–8 in progress. See the [main portfolio README](../README.md) for the full artifact roadmap.*
