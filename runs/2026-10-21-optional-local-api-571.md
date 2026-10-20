# Batch 571: optional local API selection of ares-v1.3.114

Status: actual registration, one synthetic functional job and final preservation checks completed. The new weight is an experimental optional choice on the existing local API. The default model was preserved. This publication does not establish improved accuracy.

## Exact candidate

- Model: ares-v1.3.114
- Weight SHA-256: d1b0d7978483d69714a906f5c27df14ca7fe5d20a265bc7f1fdcf6b2cb445b3d
- Training origin: [actual batch568](2026-10-21-native645-training-568.md), 30 epochs,4,080 TRAIN forwards,271 measured updates
- Selection: epoch9/order8, original VAL80 TP/1 FP/5 FN
- Saved parameters:34 P2 tensors changed;499 original entries preserved
- Fixed scoring: [actual batch570](2026-10-21-fixed-regression-570.md)

The metadata records645 image/label pairs,544 TRAIN images and997 aggregate annotations. New20 TRAIN images comprise15 positive images with26 source-only LLM boxes plus5 empty images. Inherited15 hybrid proposal/visual-review rows contain30 boxes;997 is not a count of independently produced source-only LLM annotations. Source is LLM, human confirmation false, experimental true, stable improvement false. The synthetic metadata test uses257 updates and is not evidence for the actual271.

## Actual local preservation result

| Item | Before | After |
|---|---:|---:|
| Selectable models | 86 | 87 |
| Registry PT/JSON files | 170 | 172 |
| Prior choices preserved | 86 | 86 |
| Prior registry files preserved byte-for-byte | 170 | 170 |

The fresh baseline matched the preceding562 menu and complete registry mapping. Every prior choice and file was preserved. The default weight SHA-256 stayed f19828a02f6a5418d5e954c0c076865ac90395e748a708fb9730f201cabe6441. Shared state also remained unchanged. There was no default promotion or cloud synchronization.

Registration targeted only127.0.0.1:8775 and the existing local registry. Configured local authentication remained internal; proxy and redirect use was disabled. No source media, weights or private code were uploaded to GitHub or an external API.

## One synthetic functional job

Exactly one synthetic video was generated:2 black320x320 frames at5fps. One upload and one job explicitly selected114. The completed job used the expected weight SHA and effective YOLO/ByteTrack settings: image size640, confidence0.35, IoU0.5 and full ROI. The annotations download returned HTTP200.

This verifies model selection, effective settings and output download only. It is not an accuracy test or a motion benchmark. API neural calls were not independently instrumented. Durable exclusive intents and retained receipts prevent blind resubmission after unknown outcomes.

## Review and native evidence

One fresh independent gpt-6-astra/high source review read all13 own sources,5 named external sources and the570 curated history text: C0/I0/M0, no repairs, no rereview. Nine inherited helpers/tests remain byte-identical to closed562. All declined scopes, root rulings and costs were retained.

Native CPU metadata RED3e780e showed the prior113 policy rejecting the new114 contract; GREEN41e46a admitted the valid synthetic case and rejected29 invalid cases, including stale training counts and state drift before API access. Policy3d6a14, optional21c155, upload641769, durability2090e2 and gates95224d passed. Two earlier argument-only failures were retained and corrected by providing the required run label; no API or effect occurred in those failed invocations.

The native evidence precheck4a013a verified6,725 bindings with zero detector/API calls. Source admission59b562 rechecked all reviewed pins before sealing. Actual native terminals were prepare346025, registrationd33eb3, synthetic submission2b8a2e, synthetic completioneba273 and final preservation360edb; all exited0.

- Source seal:de173359fbe39e6a70055c7c04cc924914f4bcf5216b4650543f4479c11f01d2
- Publication plan:262a3ccfc58e3668395b7275c8b03a6a4c2a9dc0ddd4d8d2f207f0e74508787f
- Registration receipt:567d3f37557c0e6de0050e5908f514d182a016fd76cfe94aae6a472862dd7759
- Publication preservation/functional acceptance:e89cc94ec3f83e2f3247b8fd3c7cff39e8f8b80afd7986f9ca3f62cc34d64843
- Closed571 manifest:9429e08284c95e31d8ccac1329b5aee22ccbdb88e11b36c12aa96449c2611d53
- Closure:1d5ede exit0,53 own files,6899 external bindings;zero checker detector/API calls

The publication acceptance artifact concerns preservation and function. It does not satisfy the final accuracy gate.

## Quality limitation remains

Consumed fast scoring stayed45/2/7 versus113. Large-cohort counts changed323/33/1 ->320/26/4: precision90.7303% ->92.4855%, recall99.6914% ->98.7654%, empty-frame FP2 ->1. B3QC and Wm sessions lost true positives. Historical qualification, per-session nonregression and stable improvement remain false.

Final acceptance still requires at least3 unused shooting sessions and300 source-only LLM boxes frozen before candidate predictions, precision AND recall >=90% at confidence0.35/matching IoU0.5, with per-session results, empty-frame false positives and exclusions. Consumed regression and synthetic smoke provide zero new independent final-group credit.

This record contains curated Markdown only, without local paths, credentials, raw logs, media, weights or private source code.
