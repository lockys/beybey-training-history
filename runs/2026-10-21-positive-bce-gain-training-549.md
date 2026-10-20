# Positive-only BCE gain trial 549 — completed, no qualified candidate

Recorded 2026-10-21 (Asia/Taipei). Goal: improve missed Beyblade detections during fast movement/X Dash. **Stable improvement remains unproved.**

## Actual training and decision

The seed-42 run completed normally: **30 epochs, 3,870 actual TRAIN forwards and 258 actual main optimizer updates**. Its separate, discarded GPU preflight performed one TRAIN forward and one optimizer update, with zero completed epochs/checkpoints. These are 259 updates when both are counted; preflight parameters were not reused for main training. No actual model attempt was retried.

Relative to the successful-training recipe in [trial 539](2026-10-20-native-positive-training-539.md), the sole learning change was multiplying positive classification BCE by 2 while keeping the **original soft target values**. Zero-target background weighting, TAL assignment, box/DFL weights, normalization, sampling, initializer and fixed VAL selector were retained. This differs from the rejected target-floor trial [545](2026-10-20-positive-target-floor-training-545.md).

All 228,860 observed positive terms were scaled. Original target sums remained unchanged. The one-update GPU check confirmed exact positive/negative loss values, preserved the original 499 frozen state entries and changed only permitted P2 parameter tensors. Independent root validation checked the retained per-epoch attestations and 30 checkpoint hashes, without reloading a detector. The total of constructor, internal VAL and checkpoint-selection neural calls was **not independently counted**; 3,870 is the audited TRAIN count.

Training used the same **615 pairs: TRAIN 514, VAL 54, TEST 47**, with 775 TRAIN boxes, 951 total LLM boxes and 109 TRAIN negative images. **This trial added zero images and zero boxes.** The earlier 12 images/23 boxes from 537 are historical additions, not new data again.

## Fixed VAL outcome

The unchanged selection used 54 frames/85 LLM boxes, confidence 0.35, match/NMS IoU 0.5, image size 640 and minimum precision 0.98, then maximum recall, fewer false positives and earliest order.

| Item | Actual outcome |
| --- | --- |
| Completed checkpoint candidates | 30 |
| Qualified candidates | 0 |
| Selected checkpoint | NULL |
| Minimum / median / maximum false positives | 2 / 12 / 398 |
| Lowest-FP observation, order 21 / epoch 22 | TP 81, FP 2, FN 4 |
| Precision / recall of that observation | 97.5904% / 95.2941% |

The lowest-FP row is a posthoc observation, **not a selected or publishable checkpoint**. This single-seed, consumed-VAL experiment does not establish generalized or causal effects. Its outcome does not support retaining positive-only gain 2 as a qualified candidate under this recipe.

No `ares-v1.3.112` registry weight or metadata was created. Candidate fast/324-box regression and API publication were not started: **zero additional scoring model loads, predictions or root forwards; zero API requests**. Unexecuted accuracy results are unavailable, not zero errors. No rescue threshold or protected-reference sweep was performed.

The most recent API evidence remains trial 543: model 110 selectable alongside preserved choices, 85 choices/168 registry files. **That menu was not refreshed during this trial.** There was no default promotion.

## Source review and retained evidence

One fresh whole-package review found C0/I1/M1. The important finding was a release prerequisite referring to different names for genuine terminal test receipts. A single root repair preserved the originals and bound byte-exact aliases; missing prerequisite 1c5bfc failed before the repair, and 3a19f8 verified actual bytes afterward. All 18 reviewed training sources remained unchanged. The historical progress-text minor finding was deferred with an explicit current-status ruling. No rereview or neural retry occurred.

Native main terminal: `0d8487` exit 0; independent root artifact check: `6aabcc` exit 0. Root checked 30 checkpoints, all 18 prospective sources, 575 declared executable sources, actual optimizer records and 30 sampler traces. The initial data-stage failure occurred before any ML; the guarded completion verified existing files without recopying them.

Closed training evidence manifest: `495251f98de1aed55584f28b1579987c7c716930b71f8d3c9f37d8c1f78f14ed`.

## Separately frozen future TRAIN data 550

Eighteen original native frames from three cached public posts by [juuh8891](https://x.com/juuh8891) were selected using previously sealed image-change statistics, then viewed before detector predictions. All 20 accepted proposal crops were reviewed at native pixel scale.

**Ten new-to-current-training images and 20 LLM boxes were retained; eight whole frames were excluded for uncertain wall occlusion.** Excluded frames are not empty negatives. An RGB pixel audit against all 615 current images found no exact collisions, including VAL/TEST collisions.

The native frame indices, PTS/time bases, source URLs and media/image/pixel hashes are retained privately. Labels are `source=llm`, `human_confirmed=false`, `review_status=pending`. They are not human-confirmed accuracy evidence. They add **zero new videos, zero camera groups and zero independent final groups**, and were not included in trial 549. Novelty is relative to the current dataset and declared canonical frame identities, not a complete all-history provenance audit. Dataset merge/training has not started.

Closed source-only evidence manifest: `2215f601adffd9baae099da774f277e369da612624959d78dca72f1f833385f9`. Preparation and validation made zero model calls.

## Bounded source discovery and remaining gate

A normal Roboflow download required login and was skipped; no images were admitted. Public search identified three further YouTube candidates: [Infinity Stadium](https://www.youtube.com/watch?v=kAJjDLWw_3w), [Double Xtreme tournament](https://www.youtube.com/watch?v=DJ-Oi_Ik2-Y) and [championship burst-finish footage](https://www.youtube.com/watch?v=UukZSf-uFTw). These are **metadata-only candidates**: no downloads, original-frame inspection, labels, admitted training media or established independent sessions. The known qualitative-only source remained excluded.

The goal remains active. Final acceptance still requires at least **three unused shooting sessions and 300 pre-frozen LLM boxes**, with both precision and recall at least 90% at confidence 0.35/one-to-one IoU 0.5. Current consumed references and same-camera additions do not satisfy that gate.

Only this curated Markdown is published. No media, weights, private source code, personal data or credentials are uploaded in this history commit.
