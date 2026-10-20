# Batch 570: fixed regression scoring of ares-v1.3.114

Status: actual scoring, independent saved-prediction recount and immutable local evidence closure completed. The fast subset did not improve. False positives decreased, but the large cohort gained three misses compared with 113. Stable improvement remains unproven. Optional API publication is a separate pending preservation phase.

## Candidate and actual execution

The exact weight selected by [batch 568](2026-10-21-native645-training-568.md) was scored once: ares-v1.3.114, SHA-256 d1b0d7978483d69714a906f5c27df14ca7fe5d20a265bc7f1fdcf6b2cb445b3d. Its training origin remains 30 epochs, 4,080 TRAIN forwards and 271 measured optimizer updates. Selection used epoch9/order8, with VAL80 TP / 1 FP / 5 FN.

Actual scoring completed with 8 model loads, 244 predictions (175 CPU / 69 GPU), and 251 observed root forward entries. It performed no training, optimizer updates, API requests or shared-state writes. The independent root checker used no detector and recounted candidate and cached110/113 raw predictions against frozen references. Baseline inference was not rerun.

All six scoring/export/matching/audit/monitor helpers remained byte-identical to closed561. Confidence0.35, one-to-one matching IoU0.5, NMS IoU0.5, image size640, max detections300 and no arena filter were unchanged. The evaluation included241 labelled frames plus3 arena-only frames. These are consumed LLM references, not fresh blind accuracy.

## Comparison with actual113 saved predictions

| Consumed cohort | Model | TP | FP | FN | Precision | Recall | Empty-frame FP |
|---|---|---:|---:|---:|---:|---:|---:|
| Fast subset | 113 | 45 | 2 | 7 | 95.7447% | 86.5385% | n/a |
| Fast subset | 114 | 45 | 2 | 7 | 95.7447% | 86.5385% | n/a |
| Six cases | 113 | 77 | 11 | 9 | 87.5000% | 89.5349% | n/a |
| Six cases | 114 | 77 | 4 | 9 | 95.0617% | 89.5349% | n/a |
| Large175frames/324boxes | 113 | 323 | 33 | 1 | 90.7303% | 99.6914% | 2 |
| Large175frames/324boxes | 114 | 320 | 26 | 4 | 92.4855% | 98.7654% | 1 |

The fast subset retains7 misses. Across the large cohort,114 removed7 false positives but lost3 true positives: precision +1.755212 percentage points, recall -0.925926 points. This is a precision/recall tradeoff, not a stable improvement.

| Large-cohort session | 113 TP/FP/FN | 114 TP/FP/FN |
|---|---|---|
| youtube-y5WmT7RSl4A | 54/2/0 | 54/1/0 |
| youtube-B3QCzjTKDLs | 37/14/0 | 35/10/2 |
| youtube-Iaoe6DA-680 | 144/0/0 | 144/0/0 |
| youtube-Wm-TzWxswg8 | 88/17/1 | 87/15/2 |

Per-session nonregression against113 is false. Comparison with110 was also retained: fast45/2/7 unchanged; large321/49/3 ->320/26/4, precision +5.728792 points and recall -0.308642 points. The original332/333 qualification gates were not rebased; historical qualification is false.

## Evidence and limitations

One fresh independent source review read all13 own and4 named external sources, with C0/I0/M0. It independently hashed126 cached baseline bindings, the selected114 weight and575 vendor files, and separately recomputed cached110/113 counts using stdlib matching. It did not rerun reviewed scripts or establish runtime accuracy. Root rulings retain all declined scopes and costs.

Seven CPU verification receipts were sealed. The native runtime admitted6,652 inputs. Actual native terminals: scoring99e8e9 exit0, independent root90270d exit0, closurea6a6c4 exit0. The closed evidence contains67 own files,3,982,097 bytes and6,657 external bindings.

- Closed570 manifest:9fb9babc1cf69a0afd43c5a79af457b573630d1a2799ef0029c55f61254a4677
- Source release:ecb0db3a25680e3e2ed2a038267c157070a950963eae67363d18a34b936880e0
- Input declaration:af96f16b2822ffcc609b534e19150b77979ce306d3b10a895f2bec5cb173d6fb
- Actual568 training manifest:1857ce0c007111b7ca4318e0675a994da5cc0ead5a97bb6e2986925f594fe1c8

Training provenance remains645 pairs and997 aggregate annotations; new20 TRAIN images contain15 positive images/26 source-only LLM boxes plus5 empty images. Inherited15 hybrid proposal/visual-review TRAIN rows contain30 boxes; the997 aggregate is not997 independently produced source-only LLM annotations. No human confirmation or fresh final-group credit is claimed.

Final acceptance still requires at least3 unused shooting sessions and300 source-only LLM boxes frozen before candidate predictions, precision AND recall >=90% at confidence0.35/matching IoU0.5, with per-session results, empty-frame false positives and exclusions. Human confirmation is not required. Consumed regression material supplies zero new independent final groups.

This record uploads curated Markdown only. No source media, weights, private source code, raw logs, local paths or credentials are included.
