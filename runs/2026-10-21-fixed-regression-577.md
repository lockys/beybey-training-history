# Fixed regression 577: ares-v1.3.115

115 completed one fixed scoring entry and independent raw-result validation. The experiment did not demonstrate stable improvement. Fast-related aggregate counts did not improve, and false positives increased in the larger cohort.

The selected weight is ce79428b8e5d783258c00570fdff6e7df9cf6809f5e15353859691d337b52092, produced by [training575](2026-10-21-native659-training-575.md): 30 epochs, 4,200 TRAIN forwards, 280 actual optimizer updates, selected order19/epoch20. Its consumed VAL result was 81/1/4. That selection result is separate from this fixed regression.

## 114 to 115

Counts are TP / FP / FN against frozen LLM references.

| Cohort | 114 | 115 | Precision 114 to 115 | Recall 114 to 115 |
| --- | --- | --- | --- | --- |
| Fast-related | 45 / 2 / 7 | 45 / 2 / 7 | 95.7447% to 95.7447% | 86.5385% to 86.5385% |
| Six-case | 77 / 4 / 9 | 77 / 18 / 9 | 95.0617% to 81.0526% | 89.5349% to 89.5349% |
| Large cohort | 320 / 26 / 4 | 322 / 49 / 2 | 92.4855% to 86.7925% | 98.7654% to 99.3827% |

Large-cohort empty-frame FP increased from one to three. Two additional TP came with 23 additional FP. Per-session nonregression against 114 is false. Historical qualification is false.

| Large session | 114 TP / FP / FN | 115 TP / FP / FN |
| --- | --- | --- |
| youtube-y5WmT7RSl4A | 54 / 1 / 0 | 54 / 20 / 0 |
| youtube-B3QCzjTKDLs | 35 / 10 / 2 | 36 / 14 / 1 |
| youtube-Iaoe6DA-680 | 144 / 0 / 0 | 144 / 0 / 0 |
| youtube-Wm-TzWxswg8 | 87 / 15 / 2 | 88 / 15 / 1 |

Nineteen of the additional 23 large-cohort FP are in y5WmT7RSl4A. Equal aggregate fast counts alone do not establish the missed identities. Subsequent read-only diagnostic578 separately confirmed the same seven frame/object FN identities across110,113,114,115, using retained results and unchanged references with zero neural calls or media exports. Five are consecutive kfvz452-456 frames with no proximity-only candidate at0.35. Two are iwhh869/871, with nearby boxes at IoU0.47644592574586286 and0.47338250407974025. These are correlated frame/object misses, not seven independent events. No retained lower-confidence predictions were available, so threshold failure remains unproved.

## Cached comparisons and fixed protocol

The retained 110 and 113 results were also independently recounted from cached predictions, with no baseline model reruns.

| Model | Six-case | Fast-related | Large cohort | Large empty FP |
| --- | --- | --- | --- | --- |
| 110 | 77 / 4 / 9 | 45 / 2 / 7 | 321 / 49 / 3 | 3 |
| 113 | 77 / 11 / 9 | 45 / 2 / 7 | 323 / 33 / 1 | 2 |
| 114 | 77 / 4 / 9 | 45 / 2 / 7 | 320 / 26 / 4 | 1 |
| 115 | 77 / 18 / 9 | 45 / 2 / 7 | 322 / 49 / 2 | 3 |

The original332/333 qualification criteria remain unchanged. Cached comparisons do not rebase that gate. Reference pixels, boxes, confidence0.35, one-to-one IoU0.5, NMS IoU0.5 and image size640 remain fixed. Six scorer helpers are byte-identical to their closed561 counterparts.

## Actual execution and evidence

One selected115 entry completed with eight model loads, 244 predict calls and 251 recorded root forward calls: 175 CPU predictions and 69 GPU predictions. It scored 241 labelled frames and three arena-only frames. The independent checker executed zero model loads or neural forwards, and verified native identity, the terminal/observation chain, actual ledgers, saved predictions, ratios, empty FP and per-session totals.

This step added zero TRAIN epochs or optimizer updates. It made zero API requests or shared-state writes, and performed no default or cloud promotion. There was no restart, resume, retry or output reuse. The 8,200 frozen input bindings and 575 executable bindings were checked before entry.

A single fresh source review covered 13 own sources, five named external sources and the complete curated training575 history. It found C=0/I=1/M=1. The Important receipt-binding gap was repaired once: sealing and declaration admission now require the complete exact eight-receipt map to match the reviewed prospective evidence. Metadata-only RED demonstrated eight invalid admissions before the fix; GREEN rejected those changed, omitted and additional bindings afterward. The original eight receipts and reviewed snapshots were preserved. There was no rereview.

The Minor limitation is explicitly deferred: downstream root validation accepts the current selected115 snapshot; general end-to-end NULL closure is not established. This does not affect the actual selected115 result. A future NULL outcome needs a separate zero-inference validation branch.

- Closed training575 manifest: 2498ed2e4eabb817e78c4e77b6587483a3667f52bd1f56f66b10b34111eddafb
- Scoring source release: d7a8f975f590f837f1a7f4fd479ceca1017107854fffb865c44ca4aa21562a4f
- Scoring input declaration: 06d3e7209ffae40538c3d78b9947489d492193f8c083b5f69748e6376c1caea7
- Closed scoring577 manifest: 4af57ef80b69f850267cccd86203bdd4a645292c7a28930b9633740a61efe2db
- Subsequent zero-inference diagnostic578 manifest: a70ab5bbba162db67de3e24dd616ba9a8b3efdc91e2d78054f01442680dcd404

## Limits and next work

These are consumed regression results against LLM references, not new independent-session acceptance, human-confirmed truth or physical-device validation. source=llm, human_confirmed=false, new_independent_final_groups=0, stable_improvement_proven=false.

Independent GPU elementwise gradients, native binary integrity, prior training tensor replay, raw VAL replay and all-history camera novelty remain outside the assurance provided here. The controlled data change and measured extra updates do not isolate a single cause of the FP increase.

With the identities separately checked, the next diagnosis should compare confidence and box geometry while preserving this benchmark's thresholds and references. Any low-confidence probe is a separate diagnostic, not a replacement accuracy metric. Uncertain excluded images must not be converted into negative labels.

115 has not been published to the local API in batch577. Any later optional experimental publication requires its separate review and must preserve existing choices, default and state. These results do not justify default promotion.

Stable improvement remains unproved. Final acceptance still requires at least three unused shooting sessions and at least300 source-only LLM boxes frozen before predictions, precision and recall both at least90% at confidence0.35/one-to-one IoU0.5, per-session results, empty FP and exclusions. Human confirmation is not a blocking prerequisite.

Only this curated Markdown is intended for the designated history repository. Raw media, images, labels, weights, private code and raw logs are not included.
