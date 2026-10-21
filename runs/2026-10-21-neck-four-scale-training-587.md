# 2026-10-21: Neck and four-scale training, model117 (batch587)

Status: actual training completed and was independently audited. A VAL-selected experimental weight exists. Fixed X Dash/regression scoring and optional API publication are still pending; stable improvement is not claimed.

The single seed42 run completed 30 epochs, 4,200 TRAIN tensor forwards, 280 optimizer updates and 6,075 observed DetectionModel.__call__ roots in 1,458.852 seconds. Native904061 exited0, independent stdlib checker118dc1 exited0, and closer a03c81 exited0. No restart, resume or NN preflight occurred. The 10,000 ceiling covers observed module-call roots; direct constructor forwards are not independently budgeted.

Selected ares-v1.3.117 has SHA256 789ca723ad0dac108e07e10f046738d925fd67e9ec27b90ed42a112942d0bd21. The unchanged VAL rule (precision>=.98, then maximum recall, fewer FP and earlier epoch) selected order7/completedepoch8: 81TP/1FP/4FN, from27 qualified of30 checkpoints. Compared with116's selected80/1/5, this is one fewer VAL miss with the same FP count. This selected validation result is not independent test or X Dash improvement evidence.

Training started from selected116, SHA256 477c1ab1d6e1038a3c186c83488c5d9aba0e1f5750ac5a937a81dd93ac3f67b1. The corpus stayed at659 pairs:558TRAIN/54VAL/47TEST,1,023 boxes,847TRAINboxes and114TRAINnegatives. No new images or labels were added. Fifteen inherited hybrid TRAIN rows/30boxes remain; not all labels are source-only LLM annotations. Source=llm,human_confirmed=false.

Backbone layers0..10 and DFL remained frozen (241 state entries). Neck11..25 and the four Detect branches had169 trainable parameter tensors admitted to the optimizer. All seven parameterized neck modules13,16,17,19,20,22,25 had positive finite aggregate gradients at every280updates. The selected checkpoint changed167 allowed parameter tensors, including81 neck tensors. Original379/499 preservation was deliberately not required.

Nominal LR1e-6 was multiplied100 around the vendor step and restored afterward, for an effective initial base approximately1e-4. Input640,batch4,workers0,AMPfalse,session-balanced sampling, joint four-scale TAL and the previous negative-background focal weighting were retained.

One fresh whole-package review covered12 own/18 named external source bodies,2,665 declared input hashes,630 executable-source hashes and CPU receipts. Findings C0/I1/M0. Before NN, root fixed the old LR guard that rejected newly trainable neck parameters and replaced a bypassing CPU fixture with the real guarded/LR wrapper around a fake vendor parent/optimizer. Old helperRED08c99b exit1; repairedGREEN96f419 exit0. Frozen-gradient rejection and LR restoration on success/exception passed. One combined repair, no rereview, zero actual detector/optimizer execution in these CPU fixtures.

The independent checker rehashed30 checkpoints and input/source bindings, recounted saved assignment/gradient records and independently recomputed VAL selection. Live/saved tensor preservation comes from reviewed runtime assertions; the checker does not deserialize models or independently remeasure tensors or gradients. Native binary/pickle security and human annotation truth were not independently audited. Full app-suite QA is not claimed green.

Closed587 SHA256 be68a80ab2f45ae8c0d3719f02d005eb6b0fec31517971731f581682ae78d020:1,477 immutable own files and1,987 external bindings. Shared state, existing lease bytes and default/cloud/API settings were preserved. Model117 has not been published to the API.

Next: fixed scoring with unchanged332/333 pixels, boxes, confidence.35, one-to-oneIoU.5,NMS.5,640 and the original qualification baseline. Cached116 will be compared without baseline NN replay. Only actual selected AND scored117 can advance through later reviewed optional local API publication.

The goal remains active:>=3 unused shooting sessions and>=300 source-only LLM boxes frozen before predictions, precision AND recall>=90%, per-session results, empty FP and exclusions. Human confirmation is not blocking. This batch adds0 new independent final groups; stable improvement remains unproved.

Optional116 API history was already published once at e32783a8a5cde941cc676d7cde8e237228b8d61f, with exact immutable-byte readback. Earlier histories will not be republished.
