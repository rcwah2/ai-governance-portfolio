# Artifact 1 - Bank Credit Scoring Governance Case Study  

## Purpose	
Predicts likelihood of default; the prediction drives loan approval/denial, interest rate, and credit limit decisions.

## Model Type	
Gradient-boosted tree ensemble (e.g., XGBoost) paired with a post-hoc explainability layer (e.g., SHAP). Model type directly determines whether human oversight can be performed effectively — a loan officer can't meaningfully review a denial from a model they can't interpret. SHAP shows which factors (income, credit utilization, payment history) contributed to a denial, letting the officer judge whether it was justified. A scorecard or single decision tree would satisfy the oversight requirement natively, at some cost to predictive accuracy.

## Risk Tier	
High. A credit score affects a consumer's employment, housing, and loan terms. The burden of proving the score is wrong lies with the consumer, not the bank. A model that automates scoring could introduce systemic bias affecting a group of consumers. Even with periodic human auditing by the bank, consumers would still be impacted between audits.

## Jurisdiction	
Multi-jurisdictional, triggered by applicant location — not company location. The working assumption that jurisdiction follows citizenship (the same lens most people default to for legal residency) doesn't hold up against the Clearview AI precedent, where EU regulators asserted jurisdiction based on the location of the affected individuals, not the company's own footprint. Analogous to a consultant living in one state owing tax obligations to another state based on where the work happens, not where they live.

## Human Oversight	
Mandatory review of every denial before notification to the consumer, with documentation of whether the denial was justified — the burden of proving the score is wrong lies with the consumer, not the bank. Oversight also covers system-level monitoring: the system flags large trend changes in credit ratings for population-level review, in addition to individual denial review.

## Data Sources	
Core sources: credit bureau data, employment/income data, internal banking data. Other sources carry distinct risks: accuracy/fairness concerns for rent, utility, and telecom payment history; discrimination risk for zip code and demographic data; privacy concerns for behavioral/digital data. Zip code is excluded by policy as a proxy for race — though exclusion alone doesn't guarantee fairness, since other included variables (income, employment) can reconstruct the same signal indirectly. Bias is tested via demographic parity and equalized-odds testing, performed by the compliance team, evaluated against the four-fifths rule: ratio ≥0.90 → routine monitoring; 0.80–0.89 → escalate to committee; below 0.80 → pull from production immediately.
