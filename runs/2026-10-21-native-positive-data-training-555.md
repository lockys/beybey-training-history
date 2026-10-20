# Batch 555: native positive data with the baseline loss recipe

Status: training completed; candidate ares-v1.3.113 selected. Stable improvement remains unproven. API publication is pending fixed regression scoring and preservation checks.

## What changed

This trial retained the batch 539 / ares-v1.3.110 recipe and added 10 original TRAIN images with 20 LLM boxes from already collected footage. No new training videos or independent camera groups were added.

The dataset contains 625 image/label pairs: 524 TRAIN, 54 VAL, 47 TEST; 971 annotated boxes, including 795 TRAIN boxes and 109 empty TRAIN images. All 615 parent pairs and 202 existing VAL/TEST image/label files were preserved. See [the preceding data record](2026-10-21-native-training-data-554.md).

Label provenance matters: 15 legacy TRAIN images / 30 boxes came from YOLO11s proposals plus Codex visual review, with human_confirmed=false. The 20 newly added boxes were LLM annotations made from original pixels before candidate predictions. The aggregate 971 boxes must not be described as 971 independently produced LLM boxes. LLM labels remain source=llm, human_confirmed=false, review_status=pending.

## Actual execution

- One fresh seed-42 run, 30 completed epochs, 3,930 TRAIN tensor forwards and 262 measured optimizer updates; elapsed 1,183.03 seconds.
- Separate discarded GPU preflight: 1 TRAIN forward / 1 optimizer update, 0 completed epochs and 0 checkpoint saves. The main run started from the original initializer.
- Total measured TRAIN work including preflight: 3,931 forwards / 263 updates. Constructor, VAL, TEST and checkpoint-selection calls were not independently counted as a total.
- P2 training only; 499 transferred state entries preserved. The selected checkpoint changed 33 allowed P2 parameter tensors.
- Stock positive soft-target BCE retained. Negative focal gamma 2, floor 0.5; original assignment, bounding-box loss, DFL and normalization retained. Exact GPU elementwise loss/gradient equality was not instrumented in this baseline preflight.
- Batch 4, image size 640, workers 0, AMP off, warmup 1 epoch, mosaic off, session-balanced sampling; the existing actual-step learning-rate multiplier 100 was retained.
- One independent source review: 0 Critical, 0 Important, 1 deferred Minor concerning historical aggregate label wording. No source repair or rereview was required.

## Fixed VAL selection

The existing VAL cohort has 54 frames and 85 reference boxes. Settings were fixed before training: confidence 0.35, one-to-one matching IoU 0.5, NMS IoU 0.5, image size 640. Candidates require precision >=98%; selection then maximizes recall, minimizes false positives and breaks ties by earlier order.

| Candidate | Selected epoch | TP | FP | FN | Precision | Recall |
|---|---:|---:|---:|---:|---:|---:|
| Baseline ares-v1.3.110 | 7 | 81 | 1 | 4 | 98.78% | 95.29% |
| New ares-v1.3.113 | 12 | 81 | 1 | 4 | 98.78% | 95.29% |

All 108 VAL image/label hashes and selection settings match the baseline. The selected VAL counts did not improve. Only 1 of the new run's 30 checkpoints met the precision gate; the baseline had 3. These are exploratory comparisons against existing LLM references, not fresh blind or human-verified accuracy.

Selected weight SHA-256: 4bd24007084abaaa2f81a8e6d93624f49b5c70f1f6c7beb147a7d17360d5428d.

The independent root audit checked native launch/nonce/terminal linkage, all 30 checkpoint hashes, 3,930 batch records, 262 optimizer records, 30 sampler traces, 18 experiment sources and 575 declared executable files. The audit itself loaded no detector.

## Separate public video collection

Batch 557 acquired two predeclared public videos once each, both at 1280x720, totaling 145,884,585 bytes. Batch 559 exported and verified 16 original overview frames, 8 per video, with native PTS, global decoded index, source URL and image/RGB hashes. Each source retains 32 export slots under its 40-frame limit.

- [zankye: Phoenix Wing / Phoenix Feather speed battle](https://www.youtube.com/watch?v=FU6WlLzsMwY): 577 seconds; SHA-256 908c180abedafc81c474daf482e3066481fc1367b79f3b19772e3c7adc29f396.
- [BeybladeGeeks: Double Xtreme stadium review and battles](https://www.youtube.com/watch?v=_hokxdEiiUc): 641 seconds; SHA-256 5b08568578c5c7a29bf9fce19132af888552ca20a19cfb8933ef16d803a42c64.

The overview reveals low-angle motion, occlusion/score overlays, stadium reflections, a center rotor and assembled spinning/still bodies. Scene contacts are not bounding-box references. No formal LLM labels, model calls, training admission or independent acceptance groups were created in these collection phases. Different video IDs or creators do not prove distinct shooting sessions. Reported licenses were unavailable; media remains local and is not redistributed here.

## Remaining work

This training phase made zero API requests and did not publish the selected weight. Fixed fast/old regression scoring for 113 has not yet been performed. The exact selected weight can proceed to optional API registration after that scoring and preservation review.

The goal remains at least 3 unused shooting sessions and 300 LLM reference boxes frozen before predictions, with both precision and recall >=90% at confidence 0.35 / one-to-one IoU 0.5, plus per-session results, empty-arena false positives and exclusions. This run adds 0 independent final groups and does not establish stable improvement. The goal remains active.
