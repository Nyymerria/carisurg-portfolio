# Decision Journal — Week 7 Model Choice
**Date:** 2026-07-21 · **Project:** CariSurg Triage Classifier · **Phase:** 3 candidate selection

## Context
- The Week 6 Logistic Regression baseline caught only 3 of 16 truly critical (ESI 1) patients in the test set — the ED Board and Dr. Reyes flagged this as the priority to fix before considering deployment.
- With the baseline passed and approved, the brief for this week was to test whether added model complexity is worth its cost in compute and interpretability, not just to chase the highest accuracy.

## Alternatives considered
- **Gradient Boosting (HistGradientBoostingClassifier):** fast to train (8.2s) and predict, but ESI-1 recall (0.312) fell well short of the Random Forest, and it has no built-in feature-importance output — a real interpretability cost with no offsetting benefit.
- **Small MLP:** the best accuracy (0.638) and macro-F1 (0.498) of the four models tested, but took ~103 seconds to train (≈14× the Random Forest) and tied Gradient Boosting's weaker ESI-1 recall. No usable interpretability story at all.
- **Keeping the Week 6 baseline unchanged:** the safest, cheapest, most explainable option, but its 0.188 ESI-1 recall was the exact problem this week set out to address.

## Decision
Recommend the tuned Random Forest as the Phase 3 candidate, conditional on a fuller hyperparameter search, a subgroup fairness audit, and clinician-in-the-loop review before any deployment step.

## Reasoning
- It roughly doubles the number of truly critical patients caught (3 → 8 of 16 in testing) and shrinks the worst error — patients downgraded all the way to "emergent" instead of "resuscitate" — from 11 to 6.
- Training cost is trivial (~7 seconds) and it runs on the same plain CPU environment already serving the baseline — no new infrastructure ask for Martina Griffith's team.
- It passes a genuine one-minute interpretability test: a real test-set patient (stroke alert, BP 156/138) was correctly flagged, and `feature_importances_` explains why in language a clinician can sanity-check.

## Things I do not yet know
- Whether a fuller hyperparameter search (the one run here was deliberately narrowed for available compute) would meaningfully change this recommendation.
- Whether the Random Forest's errors are evenly distributed across demographic subgroups — no fairness audit has been run on any model in this project yet.
