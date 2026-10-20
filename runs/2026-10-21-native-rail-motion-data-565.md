# Batch 565: source-only rail-motion training data

Status: the expanded dataset was built and independently verified. No new model was trained in this phase. Stable improvement and independent final acceptance remain unproven.

## Frozen reference 563

All 32 predeclared dense original frames from the previously acquired Double Xtreme source were viewed before candidate predictions. Initial body crops were reviewed; one masked body frame was excluded and one tilted body's box was extended to include its attached visible red tip.

The frozen reference accepts 20 original images with 26 source-only LLM boxes, including 5 visible empty arenas. Twelve whole frames were excluded (37.5%): unresolved clipping, overlap/occlusion, severe blur across a rail, transition/burst ambiguity, or a non-arena battery demonstration. Unknown frames were not turned into empty negatives. Full original PNGs, native PTS/global indices, URLs, video/image/RGB hashes and exclusion reasons were retained.

The entire video is TRAIN only. Labels remain source=llm, human_confirmed=false, review_status=pending. These are approximate visual annotations, not human-verified truth. All 625 parent image rasters were checked: no exact new/current pixel collision was found. This does not establish complete all-history novelty or a new independent camera group.

This source had already reached its 40-original-frame export cap. This annotation phase performed no new download, decode or native export; its crops were review artifacts only.

## Actual dataset build and independent verification

| Quantity | Parent | Expanded |
|---|---:|---:|
| Image/label pairs | 625 | 645 |
| TRAIN images | 524 | 544 |
| VAL images | 54 | 54 |
| TEST images | 47 | 47 |
| Annotated boxes | 971 | 997 |
| TRAIN boxes | 795 | 821 |
| Empty TRAIN images | 109 | 114 |

The addition is 15 positive images / 26 boxes plus 5 actual empty arenas. All 625 original pairs (1,250 files) were byte-preserved. All 202 original VAL/TEST image/label files and their split assignments were preserved. The new whole video contributes one TRAIN session group; it contributes zero independent final groups.

An independent checker opened all 645 image rasters, parsed output labels, verified all 26 new box coordinate round trips, native PTS/URL/media/image/RGB bindings, zero new pixel collisions, exact output membership and maximum-existing-index-plus-one provenance indexing. Empty labels contain zero bytes. Shared state and the existing API/default were unchanged.

The dataset still includes 15 legacy TRAIN images / 30 boxes from YOLO11s proposals plus Codex visual review. The aggregate 997 annotations must not be described as 997 independently produced source-only LLM boxes.

The old dataset admission policy rejected the new fixture in a native RED test. The updated observable contract accepted it and rejected 60 count/type/split/leak/teacher/human/extra-claim mutations. These CPU tests, the build and the checker loaded no detector and performed no optimizer updates.

## Separate bounded collection 564 and overview 566

Two newly discovered public videos were each acquired anonymously once, at 1280x720, with a 350 MiB source cap and no login/cookies/retry. No authentication or rate gate was encountered. Total media size: 132,872,736 bytes.

- [zankye: This Beyblade X Combo Makes Every Battle Easy...](https://www.youtube.com/watch?v=SMb85H1izpg): 662 seconds, 67,050,292 bytes; actual upload metadata 2026-06-19. SHA-256 12e866d833c15f357d1ef4a355a76524a082cdc5cb31bf8db77c95e3462d4c85.
- [zankye: The first X Beyblade released is still the best](https://www.youtube.com/watch?v=Z6Pjk7m5280): 606 seconds, 65,822,444 bytes; actual upload metadata 2025-10-09. SHA-256 3a8a6ecad00b4f32b7f380c94c8e4ec25c7cb292122b34aaf9b6ffcf16c4e57b.

One native sequential overview decode per source exported 8 originals each, 16 total. PNG/RGB hashes and native PTS records were independently verified. Each new source retains 32 slots under its 40-original-frame cap.

Scene contacts show overhead and low-angle battle views, product/hand shots, and a tournament/studio edit. These are unassigned source candidates with zero formal boxes, training admission or final-group credit. Upload dates, video IDs and creators alone do not prove distinct shooting sessions. Low-angle portions remain stress candidates; filming-session provenance and overhead suitability still need admission. Media licenses were not reported, and media stays local.

## Evidence and next step

- Closed reference 563: 40cd63a5f4e19b06227768c8fdad6199781e8e25cf7c328243b0b0b0e41100c1.
- Frozen reference SHA-256: 50719cc6c572f7dcd5dcee9e3803ffe37a2458a08a9e80b563fed3bbe603ee45.
- Closed dataset 565: 885c5e9819eb6f8af90297cb39177baf029b83a66e709ce94468f68c3730ae86.
- Dataset manifest SHA-256: 05f5451a72bad8be577345280cc07f3810a6a7a070442252b9ea82cd5d53d43e.
- Closed acquisition 564: 3c5bc502c2fdee2202da66382c320540868f1b45e6d95aa44b8f5e10d5562b53.
- Closed overview 566: a9dfee5799f1866fdca406cb5ce03e59c4d1d81739e5035c8b4acf19b6b422df.
- Native build 51b48e; independent dataset check 46de0e; contract RED b97454 / GREEN bb91dc.

The next candidate will retain the baseline training recipe to measure this data addition separately. It requires its own source review and actual neural execution. No model114 weights or API choice were produced by this data phase. [Model113 remains the previously verified optional choice](2026-10-21-optional-local-api-562.md).

Final acceptance remains at least 3 unused shooting sessions and 300 source-only LLM boxes frozen before predictions, with both precision and recall at least 90% at confidence 0.35 / one-to-one IoU 0.5, plus per-session results, empty-arena false positives and exclusions. Human confirmation is not required. The full goal remains active.
