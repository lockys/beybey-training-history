# Batch 561: fixed regression scoring of ares-v1.3.113

Status: actual scoring and independent saved-prediction recount completed. Aggregate old-cohort results improved, but the fast subset did not improve and one session regressed. Stable improvement remains unproven. Optional API publication is a separate pending preservation phase.

## Candidate and execution

The exact weight selected by [batch 555](2026-10-21-native-positive-data-training-555.md) was scored once: ares-v1.3.113, SHA-256 4bd24007084abaaa2f81a8e6d93624f49b5c70f1f6c7beb147a7d17360d5428d. Its training origin remains 30 epochs, 3,930 TRAIN forwards and 262 measured updates; selected epoch 12 had 81 TP / 1 FP / 4 FN on the original VAL cohort.

This scoring entry performed 8 model loads, 244 predictions (175 CPU and 69 GPU), and 251 observed root forward entries. It performed no training, optimizer updates or API requests. The worker completed successfully; the independent root checker then loaded no detector and recounted saved predictions against frozen references.

The same six scoring/export/matching/audit/monitor helpers were retained byte-for-byte from the actual 110 scoring phase. Confidence 0.35, one-to-one matching IoU 0.5, NMS IoU 0.5, image size 640, max detections 300 and no arena filter were unchanged. The evaluation recounted 241 labelled frames plus 3 arena-only frames. These are consumed LLM references, not fresh blind accuracy.

## Comparison with actual 110 saved predictions

The baseline was independently recounted from its existing saved predictions; no baseline inference was rerun.

| Consumed cohort | Model | TP | FP | FN | Precision | Recall | Empty-frame FP |
|---|---|---:|---:|---:|---:|---:|---:|
| Fast subset | 110 | 45 | 2 | 7 | 95.74% | 86.54% | n/a |
| Fast subset | 113 | 45 | 2 | 7 | 95.74% | 86.54% | n/a |
| Large: 175 frames / 324 boxes | 110 | 321 | 49 | 3 | 86.76% | 99.07% | 3 |
| Large: 175 frames / 324 boxes | 113 | 323 | 33 | 1 | 90.73% | 99.69% | 2 |

The large cohort gained 2 true positives, removed 16 false positives and removed 2 misses: precision +3.97358 percentage points and recall +0.617284 points. The fast subset's 7 misses remain.

| Large-cohort session | 110 TP/FP/FN | 113 TP/FP/FN | Result |
|---|---|---|---|
| youtube-y5WmT7RSl4A | 54/20/0 | 54/2/0 | FP -18 |
| youtube-B3QCzjTKDLs | 35/14/2 | 37/14/0 | 2 misses recovered |
| youtube-Iaoe6DA-680 | 144/0/0 | 144/0/0 | unchanged |
| youtube-Wm-TzWxswg8 | 88/15/1 | 88/17/1 | FP +2 |

Per-session nonregression against 110 is false. The separate six-case aggregate is 77 TP / 11 FP / 9 FN. The original historical qualification against the original 332/333 baselines remains false; it was not silently rebased to 110. Aggregate precision over 90% does not establish stable improvement.

## Independent verification repair

One fresh whole-package review read all 13 experiment sources and 3 external sources and found 0 Critical / 1 Important / 0 Minor issues. The Important issue was a verifier gap: copied summary fields and empty-frame FP could disagree with raw predictions while the old audit still passed. This was not evidence that the actual 110 summaries were wrong.

A single root repair left the 13 runtime sources and six scorer helpers unchanged. The external checker now derives six/fast totals from validated per-frame detections and large/session/empty-FP totals from raw predictions and frozen truth, requiring every published summary to agree for both candidate and cached baseline.

CPU tests reproduced the summary-forwarding gap, then accepted the actual 110 data and rejected 15 corruptions of counts, ratios, session summaries and empty-FP fields. No detector was loaded in these tests. The original reviewed checker, repair evidence and all declined review scopes with root rulings were retained. No rereview was performed. Source review did not approve runtime effects, fresh accuracy or API publication.

## Separate source-only batch 560

[The Double Xtreme video](https://www.youtube.com/watch?v=_hokxdEiiUc) supplied 32 additional original frames at predeclared 4-second targets from 480 through 604 seconds. Together with its 8 earlier overview exports, this source has reached its 40-original-frame cap; no export slots remain.

One sequential decode preserved native PTS, global decoded index, source URL, image hashes and decoded RGB hashes. An independent saved-pixel check verified all 32 PNGs and their provenance without another decode or model call. Source SHA-256 remains 5b08568578c5c7a29bf9fce19132af888552ca20a19cfb8933ef16d803a42c64.

The frames include rapid blurred rail movement, spinning/still bodies, interactions and empty arenas. They are source candidates only: no frozen reference, training admission, model prediction or independent final group was created. Original footage stays local and is not redistributed.

## Evidence and remaining gate

- Closed scoring manifest: 9984d9f3466fe683ac5fe07972aa125ffea46ee5997cf304c0e82065313ce502.
- Closed source-only 560 manifest: 81f5ae9d707ccc6b0f42d2fa7a83cad6de107ea23c07bc753224a622c26aaa6a.
- Input declaration: 2d15658b1341b1efb8780d00b8c088d9347a3053da99de30df49fe6314dad52c.
- Actual successful scoring receipt: 34f6fb; independent root receipt: 5a5f3a.
- Default and shared state were unchanged; this phase made zero API requests and has not registered 113.

Final acceptance still requires at least 3 unused shooting sessions and at least 300 source-only LLM boxes frozen before candidate predictions; both precision and recall must reach 90% at confidence 0.35 / one-to-one IoU 0.5, with per-session results, empty-arena false positives and exclusions reported. Human confirmation is not required. This phase adds 0 independent final groups. The training goal remains active.
