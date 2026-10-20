# Batch 562: optional local API choice ares-v1.3.113

Status: the actual selected weight was registered as an optional local API model. A synthetic job verified explicit model selection, effective settings and annotation download. Default promotion and cloud publication were not performed. Stable improvement remains unproven.

## Exact candidate

This phase publishes the exact weight from [training 555](2026-10-21-native-positive-data-training-555.md), independently scored in [regression 561](2026-10-21-fixed-regression-561.md):

- Model: ares-v1.3.113.
- Weight SHA-256: 4bd24007084abaaa2f81a8e6d93624f49b5c70f1f6c7beb147a7d17360d5428d.
- Actual training: 30 epochs, 3,930 TRAIN forwards and 262 measured optimizer updates; 625 dataset pairs / 524 TRAIN images.
- Selected epoch 12: original VAL 81 TP / 1 FP / 4 FN; 33 allowed P2 parameter tensors changed, 499 transferred entries preserved.
- Newly added training data: 10 original images / 20 source-only LLM boxes. The dataset still includes 15 legacy hybrid proposal-plus-visual-review images / 30 boxes; not all 971 annotations are independently produced source-only LLM labels.

The fixed consumed fast subset remains 45 TP / 2 FP / 7 FN, with recall 86.54%. The large old cohort improved to 323/33/1, but one session gained two false positives. Strict old qualification and stable improvement remain false. Registration is an experimental option, not an accuracy promotion.

## Actual preservation checks

The live local API baseline was checked immediately before publication. It matched the preceding accepted menu and registry bytes.

| Item | Before | After |
|---|---:|---:|
| Selectable models | 85 | 86 |
| Registry files | 168 | 170 |
| Prior choices preserved | 85 | 85 |
| Prior registry files unchanged | 168 | 168 |

The original default remained unchanged, with SHA-256 f19828a02f6a5418d5e954c0c076865ac90395e748a708fb9730f201cabe6441. Shared training state also remained unchanged. Exact final registry membership and file hashes were checked; the new model did not overwrite an old model.

One fresh independent review read all 13 experiment sources plus 5 external sources and found 0 Critical / 0 Important / 0 Minor defects. Nine helper sources were byte-for-byte identical to the preceding accepted publication phase. The reviewer independently rehashed all 68 closed scoring files and 5,032 external bindings. Review established source and evidence consistency; actual publication and final acceptance required separate native execution.

## Functional smoke, not accuracy

Exactly one synthetic two-frame black clip was uploaded and one job was submitted with model113 explicitly selected. No private footage was uploaded. Effective settings were YOLO, ByteTrack, image size 640, confidence 0.35, IoU 0.5, a full 320x320 ROI, and a 0.0-0.4 second interval.

The job completed, its model weight hash matched the exact selected113 weight, and annotations.json downloaded with HTTP 200. This proves the optional model-selection and result-download flow for this synthetic clip. It does not measure real-video detection, tracking quality, speed, or native mobile behavior.

Native successful receipts: publication 69e217; synthetic submission 5dea3e; completed job/download 8ac979; final preservation 14908f.

Closed publication manifest SHA-256: bec1eb20789080d6273a1e29fc2c131dc7f8c9c98fa475b9d1cab00b3e6058cc.

## Scope and remaining work

Only the existing local API was used. The configured credential stayed internal. No public gateway or cloud service was tested or promoted; no default model changed. Public history contains no weights, private code, media, credentials or local paths.

Final acceptance still requires at least 3 unused shooting sessions and 300 source-only LLM boxes frozen before predictions, with both precision and recall at least 90% at confidence 0.35 / one-to-one IoU 0.5, plus per-session results, empty-arena false positives and exclusions. Human confirmation is not required. This publication adds 0 independent final groups. The ongoing X Dash improvement goal remains active.
