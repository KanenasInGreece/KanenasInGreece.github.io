VERDICT: PASS

Pre-build Lean proof checking **reduced final patch acceptance** on this pinned Qwen3-Coder-30B-A3B W4A16 profile and eight-task Lean-native roster. Ordinary review of the same starting formal plans yielded 31 accepted patches in 40 assignments. The proof gate yielded 3 in 40, with two outcomes unresolved. Even if both unresolved patches had passed, C would have finished 26 patches behind B. [Private article section](/home/xenofon/local-ai/A770_Builder/results/research/lean-builder-runs/prebuild-study/scored-01/article-for-astra.html:141)

| Arm | Assigned | Resolved | Dispatched | Plan proofs passed | Patches accepted | Seconds per accepted patch | Logical tokens per accepted patch |
|---|---:|---:|---:|---:|---:|---:|---:|
| A · Prose plan | 40 | 40 | 40 | 0 | 31 | 68.1 | 57,457.9 |
| B · Ordinary formal-plan review | 40 | 40 | 40 | 0 | 31 | 120.8 | 96,065.6 |
| C · Proof gate | 40 | 38 | 3 | 3 | 3 | 1,319.9 | 957,352.3 |

I recomputed the four-cell counts and the exploratory 95% intervals from the raw rows, resampling complete matched pairs within each task for 20,000 draws and weighting the eight tasks equally. Effects and bounds are in percentage points.

| Comparison | Both passed | A only | B only | C only | Both failed | Complete-pair effect | Exploratory 95% interval | Assigned-slot bounds |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| B minus A | 24 | 7 | 7 | — | 2 | 0.00 | −17.5 to +15.0 | 0 to 0 |
| C minus B | 3 | — | 26 | 0 | 9 | −68.75 | −81.875 to −55.625 | −70 to −65 |

**Assignment and cost accounting.** The frozen schedule reconciles to 120 official slots from 132 attempts. All 91 dispatched attempts agreed with their builder result receipts on acceptance. C’s 35 resolved gate rejections remained assigned failures and contributed 3,166.9 planning seconds and 2,351,034 logical tokens. Its two infrastructure-invalid slots remained unresolved. The 12 discarded attempts were reported separately at 1,331.3 seconds and 867,890 tokens. [Manifest](/home/xenofon/local-ai/A770_Builder/results/research/lean-builder-runs/prebuild-study/scored-01/manifest.json) · [Raw rows](/home/xenofon/local-ai/A770_Builder/results/research/lean-builder-runs/prebuild-study/scored-01/attempts.json) · [Receipt audit](/home/xenofon/local-ai/A770_Builder/results/research/lean-builder-runs/prebuild-study/scored-01/receipt-audit.json) · [Results](/home/xenofon/local-ai/A770_Builder/results/research/lean-builder-runs/prebuild-study/scored-01/results.json)

**Prespecified criteria.** C missed all three thresholds. The target was at least four additional accepted patches per 40 assignments, with seconds and logical tokens per accepted patch each capped at 1.20× B. C produced 26–28 fewer accepted patches and used 10.92× the recorded seconds and 9.97× the recorded tokens per observed acceptance. Human preparation and blind-review time were unmeasured, so these ratios cover recorded machine costs only. [Frozen study plan](/home/xenofon/local-ai/A770_Builder/results/research/lean-builder-runs/prebuild-study/plan.md)

The article correctly distinguishes a proof that the **proposed algorithm** satisfies the frozen invariant from evidence that the **delivered patch** implements it. The latter comes from independent patch grading. All three dispatched C patches passed, but dispatch was itself conditional on proof acceptance. The assigned-slot comparison therefore answers the workflow question. The intervals are exploratory and conditional on the resolved pairs from these eight seeded tasks.