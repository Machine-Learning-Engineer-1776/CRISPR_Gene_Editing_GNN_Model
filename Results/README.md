# Results

These are the files the top-5 notebook produced, with what they really show.

| File | What it is |
|------|------------|
| `top5_cut_sites_predictions.csv` | 25,935 rows: the top 5 predicted cut positions for each of 5,187 test sequences |
| `crispr_top5_cut_sites_analysis.png` | Bar charts for one sequence (sequence 3742) |
| `crispr_top5_summary_analysis.png` | Heatmap of the top-5 confidences for 10 sequences |

## The real numbers

Computed from `top5_cut_sites_predictions.csv`:

| Measure | Value |
|---------|-------|
| Sequences scored | 5,187 |
| Mean top-5 confidence | 0.037 (range 0.034 to 0.039) |
| Mean top-1 confidence | 0.038 |
| Sites above 0.8 confidence | 0 |

What "confidence" means here: the model gives a softmax score to each of 30 positions in a sequence. The CSV keeps the 5 highest. If the model had no idea, every position would get 1/30, about 0.033. A mean of 0.037 is barely above that, so the top-5 output does not yet pick out cut sites in a useful way.

The `risk_score` column and the "Safety Score" / "Risk Assessment" chart labels are just `1 - confidence`. They are not off-target or safety measurements.

There are no position-level cut-site labels in the dataset, so these rankings are not checked against ground truth.

## Removed files

Earlier versions of this folder held auto-generated summaries (executive summary, business impact report, project card, success badge, recruiter quick start, a top-5 README and an MLflow summary). They quoted projected figures such as 0.923 / 0.847 confidence, a 0.87 safety score, a 13% risk reduction and dollar savings. Those numbers were typed into the notebook as projections. They were never measured, so the files were removed. They remain in the git history.

---
Built by Ron Lance, [Alpha Peak Technologies](https://alphapeaktech.com)
