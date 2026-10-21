# Attention + neck training 118 - 2026-10-22

Campaign596 completed run 1 of 10. This is a real optimizer-backed training run,
not a fixture, replay or derived checkpoint. Native worker/launcher completed
with exit 0; a separate stdlib audit passed. The paired seed42 control run119
is subsequent work, so no paired attention effect is established yet.

Model: ares-v1.3.118 (research candidate, not published to API).
Common initializer: ares-v1.3.117, SHA256
789ca723ad0dac108e07e10f046738d925fd67e9ec27b90ed42a112942d0bd21.

Recipe: unchanged659-pair corpus,558TRAIN/54VAL/47TEST,847TRAIN boxes,
114TRAIN negatives; session-balanced sampling, seed42,640px,batch4,workers0,
AMPfalse,AdamW,warmup1,mosaic0,30epochs. Existing four-scale TAL and background
loss are unchanged. Nominal LR1e-6, actual-step multiplier100, with nominal LR
restored after every step. No new images, boxes or independent sessions.
Historical15hybridTRAIN rows/30boxes remain explicit; human_confirmed=false.

Trainable scope: attention module10, neck11..25 and Detect26 cv2/cv3.
Backbone0..9 and DFL remain frozen. Actual start measured190trainable parameter
tensors and199frozen state entries. The eight parameterized feature modules
10,13,16,17,19,20,22,25 had positive finite aggregate gradients on every actual
optimizer update. Selected checkpoint changed187allowed parameter tensors,
including102feature parameter tensors; frozen live/saved equality checks passed.
These tensor claims come from reviewed runtime checks; the stdlib audit does
not deserialize checkpoints or independently inspect their tensors.

Actual completed epochs: 30.
Actual TRAIN tensor forwards/batches: 4200.
Actual optimizer updates: 280.
Observed DetectionModel.__call__ roots: 6075 (cap10000).
Direct constructor forwards can bypass these hooks; this is not an exhaustive
universal NN-forward counter. No resume, restart or retry occurred.

VAL selection evaluated all30saved checkpoints at confidence.35, NMS.5,
640px and one-to-oneIoU.5. There were24checkpoints meeting Precision>=.98.
The unchanged ranking chose order4 (fifth epoch, epoch4.pt):
TP/FP/FN=80/1/5, Precision98.77%, Recall94.12%.
The common initializer's same VAL record is81/1/4. This selected candidate has
one fewer VAL TP at the same FP; no improvement is claimed from VAL selection.
This is agreement against consumed LLM validation labels, not independent
accuracy or a fast-trajectory regression qualification.

Selected weight SHA256:
d1dfb9212a84502607aaca1e1ecd3ad31d696cea3bf8355b12597dd7691de2bc

Completion SHA256:
dd474a5210677ab7f677768603baded517a3d29d1022fe6f2d1895a899496689

Independent record-audit SHA256:
4061325773001df44de5917983d69e249061fddfed899e46cba6b9863a3ea5de

Audit rehashed2657training inputs and630executable sources, checked13prospective
sources and all30checkpoint hashes, recomputed gradient/LR/event records and
VAL selection, and confirmed unchanged shared state/default weight. The checker
used zero model loads or NN calls. Runtime current-source provenance was checked
before training. One fresh whole-packet source review found no Critical/Important
issues; its minor stale ledger was updated and all declined scopes were ruled.
The source review is bounded, not a full vendor/pickle/label-truth audit.

Scoring the fixed fast/six-case/324-box cohorts, trajectory nonregression against
33, paired-seed comparison, ten-run ranking and API admission remain pending.
The ten planned real runs use seeds42..46 with paired attention+neck and neck-only
arms from the same117initializer. After ten actual completed runs, select at most
five eligible candidates by the prespecified trajectory ranking and fixed
per-case/session TP/FP/empty nonregression. Missing comparable evidence excludes
a candidate; fewer eligible means fewer admissions. Raw artifacts are retained.

API remains at most ten total choices including unchanged default. This run
changed no API choice or default and did not trigger a Greek rename. Jev API
requests/uploads remain zero. New independent final groups remain zero. Stable
acceptance still requires at least three unused shooting sessions and300source-only
LLM boxes frozen before predictions, P/R>=90% at.35/IoU.5, per-session empty/exclusion
evidence and real consecutive low-confidence frontend trajectories. The user's
full stable fast/blur trajectory objective remains unmet.
