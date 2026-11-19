# Scored study package for sign-off

The operator approved the revised eight-task roster. This package records the exact draft artifacts for the next approval. All evidence here comes from unscored controls.

| Task | Lean proposition | Public checks | Hidden checks | Fault detected after public checks passed |
| --- | --- | --- | --- | --- |
| prefix | [Contract](tasks/prefix/Contract.lean) | [Public](tasks/prefix/Public.lean) | [Hidden](tasks/prefix/Hidden.lean) | Stops when the remaining budget reaches zero |
| log-count | [Contract](tasks/log-count/Contract.lean) | [Public](tasks/log-count/Public.lean) | [Hidden](tasks/log-count/Hidden.lean) | Deduplicates the severity requests |
| minute | [Contract](tasks/minute/Contract.lean) | [Public](tasks/minute/Public.lean) | [Hidden](tasks/minute/Hidden.lean) | Picks the numerically largest minute among tied scores |
| interval | [Contract](tasks/interval/Contract.lean) | [Public](tasks/interval/Public.lean) | [Hidden](tasks/interval/Hidden.lean) | Keeps invalid input intervals |
| dedup | [Contract](tasks/dedup/Contract.lean) | [Public](tasks/dedup/Public.lean) | [Hidden](tasks/dedup/Hidden.lean) | Truncates the unique values to three |
| merge | [Contract](tasks/merge/Contract.lean) | [Public](tasks/merge/Public.lean) | [Hidden](tasks/merge/Hidden.lean) | Returns empty when either input is empty |
| state | [Contract](tasks/state/Contract.lean) | [Public](tasks/state/Public.lean) | [Hidden](tasks/state/Hidden.lean) | Starts from an unclamped balance |
| projection | [Contract](tasks/projection/Contract.lean) | [Public](tasks/projection/Public.lean) | [Hidden](tasks/projection/Hidden.lean) | Drops enabled rows at minute zero |

Each standalone Git bundle contains the implementation stub, public checks, and three build or Git support files. Only `Impl.lean` is editable. The task directories also hold the exact A, B, and C prompts. Arm C gains the dedicated helper. All arms use the same ordinary Lean build commands.

With Lean 4.19.0, all eight propositions elaborated. In fresh offline clones, eight stubs failed public and hidden checks, eight good patches passed both, and eight faulty patches passed public checks and failed hidden assertions. The dedicated helper emitted goals and the correct implementation hash for eight offline controls. These controls validate the fixture and specific failure coverage. The universally quantified contracts were elaborated. General correctness proofs for the eight reference implementations were outside this control round.

Fresh user cgroups measured 0.291–0.336 CPU seconds and 81,793,024–88,616,960 bytes of aggregate peak memory across the eight helper diagnostic controls. These figures include the offline sandbox and the implementation rebuild. They describe the diagnostic controls only. The optional proof checker accepted a correct projection proof and rejected the placeholder, unapproved axiom, weakened proposition, and wrong-function controls.

The manifest proposes the rehearsal limits of 900 seconds, 600,000 logical tokens, 12,000 completion tokens, and 4,096 completion tokens per response. It supplies checksums, an order seed, and 40 randomized blocks containing 120 assigned attempts. Field projection remains the low-benefit comparison. The paired analysis reports task-level outcomes and leave-one-task-out sensitivity.

Review the exact contracts, graders and limits before freezing. Effective serving sampling and end-to-end capture of optional model proof submissions remain to be verified before scored dispatch.

[Manifest](manifest-for-sign-off.json) · [Bundle replay receipts](bundle-validation.txt) · [Helper resource receipts](helper-validation.txt)

[Proof acceptance receipts](proof-validation.txt)
