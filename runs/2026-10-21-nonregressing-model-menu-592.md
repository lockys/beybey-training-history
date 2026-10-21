# Fixed-test model menu retention - 2026-10-21 (batch592)

The user approved a maximum of ten API choices including the unchanged default.
Nondefault choices require comparable saved fixed-test evidence: TP must not
decrease and FP must not increase on the fast subset and each original case and
large-session group, with no increase in each group's empty-frame FP. Equal
results are allowed. Versions lacking complete comparable evidence are excluded.
The reference baseline is ares-v1.2.2, SHA256
af7bfb9f32fe8e692cc2d928820166ba1478af1ea287d499e36f336d3da5d97b.

Nine nondefault versions passed saved-prediction recounts. Each audit covers
241 labelled frames and three excluded arena-only frames, using unchanged
references and matching IoU0.5. The original inference contract is confidence
0.35, NMS0.5 and640px. These are already consumed exploratory references;
passing this retention rule does not prove independent-session accuracy or
stable improvement, nor a monotonic ranking between retained candidates.

| Model | Fast TP/FP/FN | Large cohort TP/FP/FN | Large empty FP |
| --- | --- | --- | --- |
| ares-v1.3.114 | 45/2/7 | 320/26/4 | 1 |
| ares-v1.3.85 | 45/2/7 | 322/7/2 | 0 |
| ares-v1.3.84 | 45/2/7 | 321/12/3 | 0 |
| ares-v1.3.82 | 45/2/7 | 322/9/2 | 0 |
| ares-v1.3.71 | 45/2/7 | 321/13/3 | 1 |
| ares-v1.3.65 | 45/2/7 | 321/16/3 | 1 |
| ares-v1.3.57 | 45/2/7 | 321/20/3 | 1 |
| ares-v1.3.38 | 46/1/6 | 322/10/2 | 1 |
| ares-v1.3.33 | 47/0/5 | 322/12/2 | 1 |

The operational default remains SHA256
f19828a02f6a5418d5e954c0c076865ac90395e748a708fb9730f201cabe6441.
It is retained as the existing fallback; its accuracy is not certified by this
retention audit. The older ares-v1.2.2 baseline control is eligible but falls
outside the newest-nine nondefault cap.

Later event following the immutable batch588 history: batch589 exposed
ares-v1.3.117 as an experimental option and completed a synthetic API choice
check. That established selection/runtime compatibility, not accuracy.
Its weight SHA256 is
789ca723ad0dac108e07e10f046738d925fd67e9ec27b90ed42a112942d0bd21.
Batch588's fixed-test results remain fast45/2/7 and large322/28/2 with two
empty-frame false positives and per-session regressions. Under the newly
approved retention policy117 is excluded from the curated selectable menu.
Its weight and original history remain retained.

Actual local API readback confirmed exactly ten choices: the default and nine
IDs above, with expected weight digests, unchanged default/health, all178
registry files preserved,180terminal saved jobs and three render states
unchanged, and missing-token HTTP401. The API uses existing explicit
enable-model flags without automatic registry exposure. No old registry
manifests, model files or product code were edited. The existing tunnel was
untouched; public-tunnel reachability was not separately tested.

Maintenance stopped one verified owned gateway tree and started one replacement.
A Windows exclusive-bind readiness probe rejected TIME_WAIT after the old tree
exited. Normal Python binds confirmed both ports usable; the documented bounded
manual procedure completed the first replacement start. Actual endpoint
readback, rather than the launch receipt, established readiness. The API has no
frame-drain endpoint, so a transient arrival race is not claimed impossible.

Six CPU policy behavior tests pass. Removing the actual nine-candidate cap in
memory makes the cap behavior test fail. PowerShell syntax validation passed.
One fresh read-only whole-packet review precedes the operation. This menu audit
uses saved predictions and makes no inference requests or optimizer updates.
New independent final groups remain0; stable improvement remains unproven.

The original frozen scoring record is retained at
[batch588](https://github.com/lockys/beybey-training-history/blob/main/runs/2026-10-21-fixed-neck-scoring-588.md).
Future candidates must pass comparable fixed-test nonregression before entering
the latest-ten menu. Training artifacts and honest history may still be retained
when the candidate fails this selection gate.

Updated next objective: improve trajectories for fast, blurred tops. Compare
each ten actual training runs and select five better candidates before applying
the existing nonregression gate and ten-choice total cap. Track continuity,
missed tracking, fragmentation and identity switches need direct evaluation;
the detection-only retention results here do not establish those improvements.
A significantly improved model may adopt a new Greek-myth name after evidence
supports that claim. No new trajectory result is reported in this record.
