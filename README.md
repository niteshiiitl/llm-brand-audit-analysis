# LLM Brand Audit: Measurement Artifact Diagnosis

## The Scenario
This project simulates a core challenge in AI search measurement: separating true brand performance from measurement artifacts. When evaluating Month 1 vs. Month 2 LLM audit data for "BrandX", a naive comparison shows a massive **14.2% lift** in recommendation rate. 

However, by applying the **"denominator before delta"** principle, this analysis proves that the apparent lift is entirely an illusion.

## The Analysis Pipeline
1. **Data Ingestion:** Processed synthetic, semi-structured JSONL audit logs representing multiple AI platforms.
2. **Diagnostic Cuts:** Visualized platform coverage, revealing a severe denominator shift (loss of legacy prompts, addition of a highly biased Gemini prompt set).
3. **Matched Cohorts:** Built a strict matched cohort containing only prompts evaluated in *both* periods to ensure comparability.
4. **The True Read:** Recalculated the metric on the matched baseline, proving the true recommendation delta is **0%**. 

## Why This Matters
Observation is not explanation. If we report the naive 14% lift, the client makes decisions on false data. By documenting assumptions, enforcing strict eligibility rules, and building matched cohorts, we ensure the metric reflects the underlying business reality rather than changing audit infrastructure.

**Tech Stack:** Python, `pandas`, `matplotlib`, `seaborn` (Data generated dynamically in notebook).
