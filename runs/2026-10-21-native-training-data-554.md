# Native TRAIN data 554 and bounded video acquisition 553

Recorded 2026-10-21 (Asia/Taipei). **This is data preparation, not a new model result.** The stable-improvement goal remains active.

## Dataset actually built and checked

The separately frozen pending-LLM supplement 550 has been integrated into a new isolated dataset:

| Item | Actual count |
| --- | --- |
| Total image/label pairs | 625 |
| TRAIN / VAL / TEST | 524 / 54 / 47 |
| Total / TRAIN LLM boxes | 971 / 795 |
| TRAIN negative images | 109 |
| Added native TRAIN images / boxes | 10 / 20 |
| Original pairs retained byte-exact | 615 |
| Preserved VAL/TEST image and label files | 202 |

The single build ended with native terminal `dfc401` exit 0. Independent verification `433f4b` exit 0 checked all 625 RGB images, found zero new exact-pixel collisions, and round-tripped all 20 added YOLO boxes to their frozen native references within 0.000001 pixel numerical tolerance. Native dimensions, frame indices, PTS/time bases, source URLs and media/image/pixel hashes were retained. Existing split assignments, source entries and session roles were preserved.

The added data remain **source=llm, human_confirmed=false, review_status=pending**. The eight previously rejected frames were not admitted or treated as empty negatives. There are zero new videos/camera groups/independent final groups in this dataset addition.

Admission checks were observed RED then GREEN: the initial control admitted stale totals; the actual guard rejected 20 invalid supplements, including changed evaluation splits, canonical/pixel duplicates, missing boxes, false human claims and rejected frames.

Closed dataset manifest: `c7f41db4c52764310a57ae3ef6b06bb5f782ec33cbc817e471738f7e0bf90f58`.
Dataset split-manifest SHA: `261ea9d08a50531f8c1a62e74689430e2cbc0319973ccf850e0d3a5da1a885a1`.

**No model has trained on this 625-pair dataset yet.** This phase made zero model loads, neural forwards, optimizer updates or BEYBEY API requests. The next isolated experiment is intended to retain the established 539 loss/assignment/learning recipe and change only the added data, following a fresh whole-package source review. That future experiment is not an executed result.

## Actual bounded public video collection

Three predeclared public YouTube sources were attempted once with the project's ordinary anonymous downloader, without login, browser cookies, retries or client/proxy rotation.

- [BeybladeGeeks Infinity Stadium video](https://www.youtube.com/watch?v=kAJjDLWw_3w): one complete public MP4 obtained, 1280×720, no audio, 696 seconds, 67,360,288 bytes. SHA: `03868d20e6b94fb31a2253e546d05cd5508bdeb879cd1397f94bebe302b56cd8`.
- [Double Xtreme tournament](https://www.youtube.com/watch?v=DJ-Oi_Ik2-Y): stopped by the local size guard. Incomplete parts are retained privately and are not a complete or admitted source. No resume or retry.
- [Championship clip](https://www.youtube.com/watch?v=UukZSf-uFTw): unavailable; no retry.

The complete video's license was not reported. It is retained locally; no media is redistributed. Its camera/session role and complete prior-consumption audit are unresolved, so it does not currently count as a new independent final group.

Closed acquisition manifest: `5ef3ffbf5a50907239becf5ac3b3e7c7850dbc3fc269c665d65d30ca3f08f1ed`.

## Original-native overview 556

A separate, prospectively bounded single native decode exported eight original frames, keeping global decoded indices and exact PTS rather than reconstructing indices from FPS. The 640×360 overview tiles locate apparent arena activity around 480 and 570 seconds, alongside packaging, diagrams, detached parts and host footage.

This is **scene review only**. No boxes were created, the original images have not yet been individually reviewed for box annotation, and unknown frames are not empty negatives. Eight of the maximum 40 source-frame exports are used, leaving 32 for a separately declared follow-up. No training/final role has been assigned and no model predictions were consulted.

Closed overview manifest: `bffbcdba9c6b2805f570999e54bd5eba1e41cbbf1f0d5c63582e1febc0730f26`.

## Model/API status and remaining acceptance

[Trial 549](2026-10-21-positive-bce-gain-training-549.md) remains completed with no VAL-qualified candidate. No model 112 was created or published. This data-preparation phase did not add an API weight or refresh the API menu.

Final acceptance remains unproved: at least three unused shooting sessions and 300 pre-frozen LLM boxes, with precision and recall each at least 90% at confidence 0.35 and one-to-one IoU 0.5, plus per-session metrics, empty-arena false positives and exclusions. Current same-camera additions and unassigned new footage do not satisfy it.

Only this curated Markdown is published. Media, frames, weights, private source code and credentials remain excluded from this history commit.
