# Paired campaign 596: completed training run 122

Published 2026-10-22 Asia/Taipei. Campaign progress: 5/10 completed actual
optimizer-backed runs (118..122). Full stable-trajectory goal remains unmet.

## Actual execution and audit

Run ares-v1.3.122 used seed44 with attention10 plus neck/heads trainable;
backbone0..9 and DFL stayed frozen. Runtime measured190 trainable parameter
tensors and199 frozen state entries. Same selected117 initializer,659 pairs
(558 TRAIN/54 VAL/47 TEST),847 TRAIN boxes and114 TRAIN negatives, unchanged
sampling/loss/640/batch4/30epoch recipe and nominalLR1e-6 with actual-step x100.

Original native session23031 ended successfully at native a07802 exit0.
Launcher46316 and worker52096 were distinct. 30 epochs,4200 actual TRAIN
forwards,280 optimizer updates,6075 observed DetectionModel call roots.
Constructor-direct forward calls can bypass that instrumentation; this is
not a universal count of every possible neural operation.

Post-run stdlib audit7f9099/session34514 ->f129fd exit0 rehashed2657 training
inputs,630 executable origins,13 frozen prospective sources and30 checkpoints.
It checked assignment, per-head/per-feature gradients, restored learning rates,
sampling, root budget and unchanged fixed inputs. Zero model deserialization or
neural calls in the auditor. Exact frozen tensor equality relies on reviewed
runtime live/saved checks, not independent tensor inspection by this checker.
No restart, resume, retry or parallel neural job.

## VAL-selected checkpoint

15/30 checkpoints qualified at fixed VAL precision >=.98.
Selected order10 is the eleventh epoch, not the tenth.
Fixed conf.35/NMS.5/one-to-one IoU.5 on54 frames85 source-only LLM boxes:
TP80 / FP1 / FN5, precision98.77%, recall94.12%.

| VAL session | TP | FP | FN |
| --- | ---: | ---: | ---: |
| youtube-mI4qN8iV0h0 | 23 | 0 | 0 |
| youtube-gTx9as_nf10 | 12 | 0 | 0 |
| youtube-X8Ab_zjm5H0 | 19 | 0 | 1 |
| shark-event | 2 | 1 | 2 |
| youtube-pmEIYBfQYzQ | 24 | 0 | 2 |

Native910c27 authenticated initializer117 selection (81/1/4).
Shark lost1TP and gained1FN; other four VAL sessions and all FP were unchanged.
This is a VAL regression observation, not a final frozen six-case/large-cohort
eligibility decision. No new gate or per-model threshold/tracker tuning is added.

Stock CSVrow11 reports mAP50 .97402, mAP50-95 .70827, precision .98565,
recall .94118 at its confidence-sweep operating point. Keep these distinct
from the fixed .35 gate and from physical or independent final accuracy.
References remain source=llm,human_confirmed=false,review_status=pending.

## Identities and evaluation preparation

Selected weight SHA256:
a47c7e2e5984642ba88821c9001eb7015996ac146ccc55e8ae8f26162ede1caf
Completion SHA256:
bfcf0e1e83fae98093fd3391b723d36b5a99997b1312b89ce5445f2e0ab5d054
Root validation SHA256:
4a5c41fdf22c70ddf53664c598bf4e72373e7052b075ac87ab6c89ba5951d7e4

Separate bounded CPU analysis600 authenticated274 fixed saved-baseline files
and independently recounted original1.2.2 six-case and175frame/324box results.
It established18 actual included empty-frame FP allowances:17zero, one1FP.
Actual controls schema passed with consumed33fast47measured/35certain of52.
No new predictions, tracker replay, labels, training or candidate admission
came from that analysis. Existing source references/cohort/metric rules remain
unchanged; its explicit canonical manifest encoding is recorded locally.

Run122 has no new fast/six/324/trajectory scores yet. After ten completed runs,
evaluate every selected candidate with the same frozen detector/tracker inputs,
per-case measured/certain/identity/gap and original detection/session/each-empty
nonregression. Recommend at most5 truly eligible candidates, fewer if fewer pass;
do not force replacements. API remains capped at10 total including default.
No API choices, shared state or default changed by this run. No Greek rename.

Still0 unused independent final groups. Stable acceptance requires >=3 unused
sessions,>=300 source-only LLM boxes frozen before prediction, P and R >=90%,
per-session/empty/exclusion evidence and actual consecutive production tracking.
Jev prototypes remain offline/fake-transport only; actual Jev requests0.
Only this aggregate text is published, without media, weights, labels, private
code, credentials or full logs.
