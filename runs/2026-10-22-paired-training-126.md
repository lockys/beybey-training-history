# Training 126: paired seed46, freeze10

Observed date: 2026-10-22 Asia/Taipei.

## Actual execution
- Model ID: ares-v1.3.126.
- Campaign 596: ninth of ten actual training slots completed.
- Seed 46; initializer ares-v1.3.117, SHA256 789ca723ad0dac108e07e10f046738d925fd67e9ec27b90ed42a112942d0bd21.
- Frozen backbone modules 0..9 plus DFL; attention module10 and neck/heads trainable.
- Measured scope: 190 trainable parameter tensors, 199 frozen state entries.
- 30 completed epochs; 4,200 TRAIN forwards; 280 actual optimizer updates.
- 6,075 registered DetectionModel root entries. Constructor direct forwards are outside this counter; entries do not independently prove completed forwards.
- Original owned native training session 58412 terminated with exit0 (native chunk 9388e3). No retry or resume.
- Same immutable data/profile as the other paired slots: 558 TRAIN / 54 VAL / 47 TEST frames; session-balanced sampling; batch4; workers0; AMP false; AdamW; mosaic0; four-scale detection/TAL and fixed background loss.
- No new media, labels, final reference sessions or API changes from this slot.

## Fixed operating point validation
54 frames / 85 source-only LLM reference boxes, conf0.35, NMS IoU0.5, one-to-one match IoU0.5. These are development pseudo-label results, not human-confirmed physical accuracy.

19 checkpoints met precision >=0.98. Selection maximized TP, minimized FP, then preferred the earliest epoch. Selected checkpoint order2 (third completed epoch).

| Session | TP | FP | FN |
| --- | ---: | ---: | ---: |
| youtube-mI4qN8iV0h0 | 23 | 0 | 0 |
| youtube-gTx9as_nf10 | 12 | 0 | 0 |
| youtube-X8Ab_zjm5H0 | 19 | 0 | 1 |
| shark-event | 2 | 1 | 2 |
| youtube-pmEIYBfQYzQ | 24 | 0 | 2 |
| Total | 80 | 1 | 5 |

Fixed-threshold precision 98.77%, recall 94.12%. Initializer117 has TP81/FP1/FN4 on this same validation set: this selected weight loses one TP in shark-event; other session counts and FP are unchanged. This does not demonstrate improvement.

Stock Ultralytics CSV row3 reports mAP50=0.9792, mAP50-95=0.68443, precision=0.98651, recall=0.95294. Stock confidence-sweep metrics have a different operating point and are not interchangeable with the fixed-threshold counts above.

Selected research weight SHA256: 5335b499fd33d1dd4ed5fc84d1704ed64354c184444287b7b30f51b73619f984.

## Root verification
Original CPU-only root checker terminal b33021 exit0; checker SHA256 1432da7358b2d02f346203f989374b30486e238bb46145857598e35f42397a04.
Verified 2,657 input files, 630 executable sources, 13 prospective sources and 30 checkpoint digests; recomputed assignment, gradient, sampler, LR and selection records. The checker did not import Torch, deserialize a model or run NN inference. Frozen-tensor equality comes from the reviewed runtime record, not independent checkpoint tensor inspection.

- Training completion SHA256: 6266279585f0c268365e013482a8d1b4ebe025372a1ecf34667b958c1e7ce8ac.
- Root validation SHA256: f573fe049ababfef8312acc3187680d10e9d6a0cc729da2451cc4b0b0a029d52.
- Source release SHA256: 8b7fa95df7199a7854757a0395e7b229525fa4fd1210407025a465936999abf2.
- Frozen plan SHA256: 971106bfd98e079f730a667df79e82309077a815c71909d85cb9ab7f756e8e82.
- Shared state SHA256 remained e1ef7f380b7f51bb0489621bda0eff8bc76ec2e67dc69b3517b311945f91db43.

## Admission and remaining work
This is a completed training result, not an API admission. No six-case/324-box/each-empty/trajectory comparison has yet been produced for126. After all ten actual slots complete, the common evaluation must apply per-case/session TP nondecrease, FP nonincrease, each-empty-frame FP nonincrease and trajectory nonregression. Rank actual eligible models and recommend at most five; never force five. Keep at most ten API choices including the unchanged default.

Independent stable acceptance remains unmet: three unused sessions, at least300 frozen source-only LLM boxes, precision and recall both >=90%, and actual consecutive production low-confidence tracking. New independent final groups0. No significant stable trajectory improvement, Greek renaming, production deployment, default change or API-menu change is claimed.

This file contains aggregate training evidence only. No raw media, labels, private source code, credentials, model bytes or full logs are published.
