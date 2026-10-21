# Paired campaign 596: completed training run 123

Published 2026-10-22 Asia/Taipei. Actual optimizer-backed campaign progress:
6/10 completed runs (118..123). Stable fast/blur trajectory improvement unproven.

## Completed execution and audit

ares-v1.3.123 used seed44, freeze11: attention10 and backbone0..10/DFL frozen,
neck/heads trainable. Actual runtime measured169 trainable parameter tensors
and241 frozen state entries. Same selected117 initializer and659 pairs
(558 TRAIN/54 VAL/47 TEST),847 TRAIN boxes/114 TRAIN negatives,640/batch4,
30epochs, fixed sampling/loss/AdamW/nominalLR1e-6 and actual-step multiplier100.

Original native session83703 terminalaae16e exit0. Owned launcher36128 and
actual worker39020 were distinct. 30epochs,4200 actual TRAIN forwards,
280 optimizer updates,6075 observed DetectionModel call roots.
Constructor-directforward calls may bypass these hooks; this is not a universal
neural-operation count. No restart, resume, retry or concurrent neural job.

Stdlib post-run audit47d965/session18358 ->5fb106 exit0 verified2657 training
input files,630 executable origins,13 frozen prospective sources,30 checkpoint
hashes, assignment/sampling/per-head and per-feature gradients and restored LR.
No model deserialization or neural calls in that auditor. Frozen equality is
supported by reviewed runtime live/saved tensor checks; the auditor does not
independently inspect checkpoint tensors.

## VAL-selected checkpoint

29/30 checkpoints met fixed VAL precision>=.98. Selected order15 is the
sixteenth epoch. Fixed conf.35/NMS.5/one-to-one IoU.5 on54 frames85 LLM boxes:
TP82 / FP1 / FN3; precision98.80%, recall96.47%.

| VAL session | TP | FP | FN |
| --- | ---: | ---: | ---: |
| youtube-mI4qN8iV0h0 | 23 | 0 | 0 |
| youtube-gTx9as_nf10 | 12 | 0 | 0 |
| youtube-X8Ab_zjm5H0 | 19 | 0 | 1 |
| shark-event | 3 | 1 | 1 |
| youtube-pmEIYBfQYzQ | 25 | 0 | 1 |

Native48b379 authenticated initializer117 selection81/1/4 and paired seed44
attention-trainable122 selection80/1/5. Versus117, pmEIY gained1TP/lost1FN,
other four sessions unchanged. Versus122, shark and pmEIY each gained1TP/lost1FN;
other sessions unchanged. All FP unchanged in both comparisons. This is VAL
evidence, not a significant trajectory gain or final candidate eligibility.

Stock CSVrow16 reports mAP50 .98068,mAP50-95 .70955,P .98765,R .94076
at its confidence-sweep operating point. Keep this distinct from the fixed.35
gate and from physical/independent final accuracy. References remain
source=llm,human_confirmed=false,review_status=pending.

## Immutable identities and next evaluation

Selected weight SHA256:
951cec8774ce3bdfd87d16b8507ec60524ab640826ae6579c5172a0225fb9edf
Completion SHA256:
7787e87f55532602130b7401bf7e6596b35e87eaf1f4fd5b0cc99d05f62a5283
Root validation SHA256:
1ce0804c6cbb4c55e1cd872017fd2f24a598adc0c7784dedcfe9df08287793b2

No new fast/six/324/trajectory scores for123 yet. After allten completed runs,
authenticate selected weights and use identical frozen detector/tracker inputs,
original per-case/session/each-empty-frame TP/FP gates and per-case measured/
certain/identity/gap nonregression versus33. Rank by the frozen596 ordering;
recommend at most5actuallyeligible, fewer if fewer pass. Equality is allowed;
do not add an unplanned gate or tune parameters/labels per model.

Separate producer601 preparation passed16 synthetic CPU tests after observed
RED23behaviorfailures. A saved-data fake-callback smoke rehashed263files,
reconstructed allsix original1.2.2prediction JSONs exactly and preserved175large
frame rawcounts/predictions/confidences/emptyFP; matching-pair differences0.
Sevenfakefactory/236fakepredict callbacks were not actual NN/model loads/new
predictions/training. This partial producer has no real worker/review/admission.
Existing600 authenticated baseline has18actual empty-frame FP allowances.

No API/menu/sharedstate/default changes, new Greek name or deployment.
API remains capped at10 total choices including unchanged default.
Still0 new independent final groups. Stable acceptance needs>=3unused sessions,
>=300source-only LLM boxes frozen before prediction,P and R>=90%,per-session/
empty/exclusion evidence and actual consecutive production low-confidence tracking.
Jev remains offline/fake-transport only, actual requests0.

Only aggregate text is published. No media, weights, labels, private source,
credentials or full logs are uploaded.
