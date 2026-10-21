# Saved-input trajectory diagnostic 593 - 2026-10-22

This is a replay of ten previously trained comparators, not ten new training
runs. Six consumed development cases contain 61 reference frames, 86 boxes,
and three arena-only exclusions. The three fast windows are only 12, 9 and 5
consecutive frames. References are fallible LLM estimates, some corrected/nonblind;
there is no human-confirmed physical-identity claim.

The actual unchanged ByteTrackGuard and public image descriptors processed 610
updates under the same profile for every model. Saved detections are full-frame
confidence 0.35, NMS 0.5, 640px exports; production weak proposals below 0.35,
ROI cropping and max32 behavior cannot be recovered. This is a truncated saved
input diagnostic, not complete-video, live or production-equivalence evidence.

| Model | Fast TP/FP/FN | Measured / 52 | Certain observed / 52 | Longest same-ID run coverage | ID switches | Fragments |
| --- | --- | --- | --- | --- | --- | --- |
| ares-v1.3.114 | 45/2/7 | 43 | 30 | 75.00% | 1 | 3 |
| ares-v1.3.85 | 45/2/7 | 45 | 33 | 80.77% | 0 | 2 |
| ares-v1.3.84 | 45/2/7 | 45 | 33 | 80.77% | 0 | 2 |
| ares-v1.3.82 | 45/2/7 | 45 | 33 | 80.77% | 0 | 2 |
| ares-v1.3.71 | 45/2/7 | 43 | 30 | 75.00% | 1 | 3 |
| ares-v1.3.65 | 45/2/7 | 43 | 30 | 75.00% | 1 | 3 |
| ares-v1.3.57 | 45/2/7 | 45 | 33 | 80.77% | 0 | 2 |
| ares-v1.3.38 | 46/1/6 | 46 | 34 | 84.62% | 0 | 1 |
| ares-v1.3.33 | 47/0/5 | 47 | 35 | 90.38% | 0 | 0 |
| ares-v1.2.2 original baseline | 45/2/7 | 43 | 30 | 75.00% | 1 | 3 |

Measured coverage includes detection-backed tentative/uncertain positions;
certain observed coverage is separate. Predictions/coasting cannot fill measured
gaps. Longest-run coverage sums the longest same-ID measured run per visibility
segment and divides by eligible reference boxes; unlabelled gaps break segments.
All fast identity-transfer counts and empty FP are zero. These are not IDF1/MOTA.

The diagnostic control is ares-v1.3.33, already retained in the ten-choice API
menu. Its remaining five misses are the KFVZ green observations at frames
452..456 (maximum gap five). IWHH has 18/18 measured matches and SH76 10/10,
without switches or fragments. Recency does not identify the best diagnostic
trajectory result. No consumed reference boxes were changed.

WUX crops all exceed the common diameter profile and cannot birth tracks, so its
zero tracking coverage is structural in all_cases. Dyrn frames are sparse resets,
not continuous-video evidence. No new independent final groups were obtained.

Verification: 23 behavior tests and four vendor guard probes passed. All 60
model/case raw detection TP/FP/FN and evaluated/excluded counts reproduce the
original saved reports. Runtime origins were checked against exact file hashes.
A first attempt stopped at origin validation before any frame processing; the
input map bound workspace beytrack while runtime uses legacy beytrack. Exact
18-file runtime bindings were added (17 identical, one adapter-hook difference
reviewed), the first activation retained, and one bounded recovery completed
with native exit 0. One fresh source review had no Critical/Important issues;
all three minor issues were explicitly ruled on.

Zero model loads, new training runs, optimizer updates and NN inference.
Normal module calls, loaders, YOLO construction and socket connect paths were
guarded; zero forwards is a source-audited invariant, not an independent forward
counter. Direct forward, DNS and UDP instrumentation is outside this scope.
Torch 2.10.0+cu128; Ultralytics 8.4.146; NumPy 2.1.3; OpenCV 4.10.0; LAP 0.5.12.

Completion SHA256:
eebbda05a12a86dd92bb8ef057d5dbf47e664197d01f809ba9775faf83f39341

Cross-report validation SHA256:
16fb4cfb7e0c930ab2c5fa95405309aba3a2a43c9cb5a57be643f2580ec429fe

An additional CC-BY-SA Commons video was lawfully collected with one GET and
three predeclared previews, then excluded as unsuitable for continuous battle
trajectory analysis. It was not labelled, trained, inferred or used as an empty
negative. No raw media is included in this publication.

API configuration, registry files and default weights were unchanged in this
packet. The existing cap remains ten total choices including unchanged default;
only versions with comparable fixed per-case/session TP/FP and empty-FP
nonregression are eligible. The replay does not count toward the next block of
ten real training runs. Select up to five better qualifying candidates from that
block, without forcing admission of regressions. No Greek rename, default
promotion or stable improvement is claimed. Stable acceptance still requires at
least three unused shooting sessions and 300 source-only LLM boxes frozen before
predictions, P/R at least 90% at confidence 0.35 and one-to-one IoU 0.5, with
per-session, empty-FP and exclusions reported.
