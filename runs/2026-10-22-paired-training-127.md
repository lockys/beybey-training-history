# Training 127: paired seed46, freeze11

Observed date: 2026-10-22 Asia/Taipei.

## Actual training and verification
Model ares-v1.3.127 completed the tenth actual optimizer-backed slot of campaign596. Seed46, initializer117 (SHA256 789ca723ad0dac108e07e10f046738d925fd67e9ec27b90ed42a112942d0bd21), frozen backbone modules0..10 and DFL; seven neck/head feature modules trainable. Measured169 trainable parameter tensors and241 frozen state entries.

30 completed epochs,4,200 TRAIN forwards,280 actual optimizer updates,6,075 registered DetectionModel root entries. Constructor direct forwards are outside that counter; registered entry does not independently prove completion. Same558 TRAIN/54 VAL/47 TEST frame data and fixed paired profile: batch4, workers0, AMPfalse, AdamW, session-balanced sampling, mosaic0, four-scale TAL/detection and fixed background loss. No retry/resume or new labels.

Original owned training session5016 exited0, native06d237. Actual worker PID69812. CPU-only root audit exited0, native394623. It rehashed2,657 inputs,630 executable sources,13 prospective sources and30 checkpoints, and recomputed optimizer/assignment/gradient/sampling/LR/selection records without Torch/model deserialization or NN. Frozen-state equality is from reviewed runtime records, not independent checkpoint tensor inspection.

## Fixed validation operating point
54 frames,85 source-only LLM boxes, conf0.35, NMS IoU0.5, one-to-one matching IoU0.5. These are consumed development pseudo-label results, not human-confirmed physical accuracy.

All30 checkpoints qualified at precision>=0.98. Highest TP, then fewer FP, then earliest epoch selected order2 (third completed epoch).

| Session | TP | FP | FN |
| --- | ---: | ---: | ---: |
| youtube-mI4qN8iV0h0 | 23 | 0 | 0 |
| youtube-gTx9as_nf10 | 12 | 0 | 0 |
| youtube-X8Ab_zjm5H0 | 19 | 0 | 1 |
| shark-event | 2 | 1 | 2 |
| youtube-pmEIYBfQYzQ | 25 | 0 | 1 |
| Total | 81 | 1 | 4 |

Fixed-threshold precision98.78%, recall95.29%. The aggregate equals initializer117's81/1/4, but individual sessions differ: shark-event loses1TP/adds1FN; pmEIYBfQYzQ gains1TP/removes1FN. Aggregate equality does not establish per-session improvement.

Stock Ultralytics CSV row3: mAP50=0.97664, mAP50-95=0.70325, precision=0.9856, recall=0.94118. Those confidence-sweep metrics are a different operating point.

## Immutable identities
- Research weight SHA256: 323a5198bf4e984e5278a674033815585702d799c6864bb3716a1627aa4f3e5b.
- Training completion SHA256: 115e62c87795d4754bf8c93673ebb23a9c86f790180ad838f274ce3020d8efbb.
- Root validation SHA256: a2e0e65a53ddb7b99f2ecf926fb007fe5013c9b9b02878b9e53fca97a101c8aa.
- Worker stdout SHA256: a818f1c2f1b064d6c9f6335b664eef3b4c0bb7504b3b8ea5ed90279765401884.
- Root checker SHA256: 1432da7358b2d02f346203f989374b30486e238bb46145857598e35f42397a04.
- Source release SHA256: 8b7fa95df7199a7854757a0395e7b229525fa4fd1210407025a465936999abf2.
- Training plan SHA256: 971106bfd98e079f730a667df79e82309077a815c71909d85cb9ab7f756e8e82.

## Block status and admission
All ten actual118..127 slots are completed and root-audited. This does not admit any model to the API. A new common evaluation driver has been assembled and a ten-weight packet built; its whole-packet review and actual candidate detector/trajectory evaluation remain pending at this report.

The forthcoming fixed gate requires every case/session TP nondecrease and FP nonincrease against original1.2.2, each of18 authenticated empty frames FP nonincrease, and per-case trajectory observation/identity/gap nonregression against33. Rank actual eligible candidates and recommend at most5 per10 completed runs; do not force5. Keep at most10 API choices including unchanged default. No model/API/default/name change is claimed here.

Stable acceptance remains unmet:3 unused sessions,>=300 frozen source-only LLM boxes, P/R both>=90%, and actual consecutive production low-confidence tracking. New independent final groups0; no Greek naming or stable trajectory improvement.

Aggregate evidence only: no media, labels, private source code, credentials, weights or full logs uploaded.
