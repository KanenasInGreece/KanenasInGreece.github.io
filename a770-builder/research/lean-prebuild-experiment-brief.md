# Can a Lean-checked plan improve the local builder?

## Proposed workflow

Review the required behavior and freeze the invariant. Express the proposed algorithm as an executable Lean function and prove that it satisfies the frozen proposition under explicit input assumptions. An independent verifier checks the statement, the exact proposed definition and its allowed axioms. A failed check returns the plan for revision within a fixed budget. A successful check produces a versioned brief containing the algorithm, invariant, assumptions, and boundary examples. The builder implements that brief with the ordinary toolset. A reviewer checks the delivered patch against the same contract.

The pre-build proof establishes a property of the proposed algorithm. The final patch needs its own verification. For a Lean implementation a theorem can name the delivered function directly. For Python, C, or C++, compare real executions to the proved reference and check representation, overflow, and error behavior with language-native tests. A universal guarantee requires a verified correspondence to the delivered code.

## Experiment

Use fresh bounded bug fixes with independently agreed invariants and hidden tests. Start with an unscored rehearsal that demonstrates three cases. A plausible model that stops when a remaining budget reaches zero must fail to prove maximality on a zero-cost suffix. A corrected model must pass. An implementation that reintroduces the bug after a valid plan must fail the independent patch grader.

Use matched task/repetition blocks and randomize arm order. Freeze the original requirements and initial reviewed plan per block. Use the same builder, version, budget, examples and post-build grader in all arms. Do not mount a proof helper in the builder.

| Arm | Work between plan review and builder dispatch |
| --- | --- |
| A · Reviewed plan | Dispatch the reviewed prose plan and frozen requirements. |
| B · Formal plan with ordinary review | Encode the plan as an executable Lean model, elaborate it, and allow one bounded ordinary review and revision round. Dispatch its invariant, algorithm, and examples in a fixed brief format. |
| C · Formal plan with a proof gate | Start from the same formal model and brief format as B. Use a matched pre-build allowance for proving the invariant and revising the plan in response to proof failures. Dispatch only after the proof checks. |

The primary comparison is C minus B. It estimates the value of the proof-gated workflow over ordinary review of an equally explicit formal plan. B minus A estimates the combined change from formal modeling and the extra review round. Give B and C the same format and hide certification status from the builder, so C does not simply gain a confidence cue. Freeze the theorem separately from the planner. Charge plan preparation, failed proof attempts, and revisions to the proposed workflow.

Primary outcome is independently accepted patches per assigned task. A plan that exhausts its proof budget without dispatch contributes no accepted patch and retains its cost. A correct plan followed by an incorrect implementation also fails. Report plan rejections, repairs, proof time, builder tokens and wall time, and human minutes. Report end-to-end cost per accepted patch, including attempts stopped before dispatch. Use blinded patch review and report paired effects with intervals and task-level outcomes. Set the practical improvement and cost criteria before scoring.

This is a proposed experiment. A live test of builder impact is pending. A skill change requires the experiment result and a separate operator decision on which tasks warrant the gate.
