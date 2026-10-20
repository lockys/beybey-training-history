# Batch 574: targeted native low-angle TRAIN data,659 pairs

Status: source-only LLM reference573 and dataset574 were actually completed and closed. This is data preparation, not a new model score. No detector inference, training epochs, optimizer updates or API changes occurred in573/574. Prospective115 has not been trained or published by this record.

## Why this data was selected

[Actual114 regression570](2026-10-21-fixed-regression-570.md) left the fast subset at45 TP/2 FP/7 FN. Subsequent read-only diagnosis found the same seven frame/object misses in110,113 and114: five lacked an eligible proximity candidate in saved predictions, while two already had boxes but missed the fixed IoU0.5 gate (about0.47). Adjacent-frame misses are not seven independent events.

The new source was selected for low-angle rear-rail motion blur and difficult body localization. No predictions for this source were consulted when drawing its boxes. This selection is a training hypothesis, not evidence of improved recall.

## Source and frozen reference573

The retained public source is [SMb85H1izpg](https://www.youtube.com/watch?v=SMb85H1izpg), exact downloaded MP4 SHA-25612e866d833c15f357d1ef4a355a76524a082cdc5cb31bf8db77c95e3462d4c85. Native frames are1280x720.32 original frames were sampled around two source-only overview locations, in one decode pass.8 earlier overview frames plus32 new frames exhaust the40-frame source cap;zero remain.

Native frame index, PTS,time base1/60000,PNG SHA and decoded RGB SHA were retained. Two earlier anchor frames independently matched the current decode's PTS/RGB. No resampling, synthetic blur, new download or model-based frame mining was used.

The source contains an overhead-to-low-angle cut between native13174 and13176. Viewpoints and edited segments do not receive independent shooting-session credit.

| Source-only curation | Result |
|---|---:|
| Newly exported native frames | 32 |
| Accepted complete positive frames | 14 |
| New source-only LLM boxes | 26 |
| Empty frames accepted | 0 |
| Excluded frames | 18 |
| Excluded fraction | 56.25% |

Every accepted frame was viewed as an original image. Whole frames with clipping, unresolved occlusion or uncertain body separation were excluded with retained reasons. Excluded frames were not treated as empty negatives. Boxes cover the visible physical body and its blur, excluding detached floor shadows; no hidden or off-image extent was inferred.

Accepted native indices:13172,13174,13188,13198,30795,30799,30801,30809,30811,30817,30819,30821,30823,30825.

The entire video is TRAIN-only. Source=llm,human_confirmed=false,review_status=pending. Current645 data have no matching source ID or exact RGB image; all-history source/camera novelty was not established. New independent camera/final groups remain zero.

- Frozen reference:926254aa483899df414b732f3a3b7ab9f67b8ca9b6ca49a1916b9da4575bc910
- Frozen-reference seal:1e1f2db4842483efbb753f9f5c0266196fe2fd7bdc4e6bf522db6e473fc87c55
- Closed573:3ea3fa214ea18290dc8d7aecc7f37319300216e493de3787fb1b9666e97cf03a

Actual source terminals: decode178112,freeze53cd91,independent PNG/provenance/geometry verification1df3f5,closured9cb30;all exited0.32 PNGs/26 boxes were checked; normalization roundtrip error was at most1.1368683772161603e-13 pixels. The independent checker did not decode the MP4 again; native alignment evidence comes from the retained single-pass export and its two anchors.

Native52997e separately checked every current645 image's bytes/RGB:617 distinct RGB images,32 incoming distinct images,zero incoming/current collisions,zero incoming duplicates andzero matches to the previous overview RGBs. This is exact pixel comparison, not proof of independent cameras or sessions.

## Actual dataset574 preservation

| Item | Parent565 | Dataset574 |
|---|---:|---:|
| Image/label pairs | 645 | 659 |
| TRAIN images | 544 | 558 |
| VAL images | 54 | 54 |
| TEST images | 47 | 47 |
| TRAIN boxes | 821 | 847 |
| VAL boxes | 85 | 85 |
| TEST boxes | 91 | 91 |
| Aggregate annotated boxes | 997 | 1023 |
| TRAIN negative rows | 114 | 114 |

All645 parent rows and their split assignments were preserved. All1,290 original image/label files remained byte-identical, including all202 VAL/TEST image/label files. Only14 new TRAIN pairs were added;their26 boxes were converted from the frozen source coordinates. The new source index14 was checked as max(parent index)+1.

The independent checker decoded all659 output RGB images, checked zero new/current pixel collisions and roundtripped all26 new YOLO label boxes to the frozen source coordinates within1e-4 pixels. Native PTS/timebase,public URL,media SHA,source PNG bytes and RGB were bound. Shared state remained unchanged.

Inherited15 hybrid proposal/visual-review TRAIN rows contain30 boxes and remain human-confirmed false.1,023 is an aggregate count,not1,023 independently produced source-only LLM annotations. The historical all_LLM_annotations key remains an aggregate;the explicit independent-source-only flag is false.

Native contract REDe9f1d8 showed the prior645 contract rejecting the valid659 fixture. GREENd0be95 admitted the new fixture and rejected60 invalid cases;syntax/YAML precheckeef487 passed. Actual dataset build8ef59f,independent validation2aa5af and closure9c05d6 all exited0.

- Parent565 dataset manifest:05f5451a72bad8be577345280cc07f3810a6a7a070442252b9ea82cd5d53d43e
- Actual659 dataset manifest:876f479b1eafb7baca78b244446c2cdaf41dd931f1d0cafbd772a05bfb3ad767
- Closed574:f6c5e8e73e548ff87eb72a4b4b135dd16b1b360a57b8966b6e14ae902bc7ec91
- Closed evidence:1,334 own files and1,357 external bindings

## Remaining evaluation

The prepared data do not prove any model improvement. The next controlled trial must still pass its source admission and fresh independent review,train from the original initializer,measure actual optimizer updates,complete fixed selection and regression,and preserve existing API choices/default if a real selected new weight is later offered.

Final acceptance remains at least3 unused shooting sessions and300 source-only LLM boxes frozen before candidate predictions,precision AND recall >=90% at confidence0.35/one-to-one IoU0.5,with per-session results,empty-frame false positives and exclusions. Human confirmation is not required. These TRAIN images provide zero new independent final-group credit.

This record contains curated Markdown only,no local paths,credentials,raw logs,media,weights,raw labels or private source code.
