# Campaign596: actual ten-run detector and trajectory comparison

Observed date: 2026-10-22 Asia/Taipei.

## Result
Ten actual optimizer-backed trainings118..127 completed and were independently root-audited. The common actual detector/tracker comparison also completed and passed CPU-only raw-output recount. Eligible models0; selected models0; API additions0. Do not force five admissions. No Greek renaming or stable improvement is supported.

The best fixed VAL result was82TP/1FP/3FN on85 source-only LLM boxes, but this did not establish nonregression on the other frozen cases. Validation scores and actual trajectory acceptance are separate.

## Actual common evaluation
- Ten research weights, five seeds42..46 paired with frozen backbone boundary10/11.
-70 actual model constructor attempts, all completed.
-2,360 successful fixed-profile predict calls.
-2,420 registered root entry events, below4,720 cap. Constructor direct forwards remain outside this counter; entries do not independently prove completion.
-610 actual CPU tracker updates after the NN phase was permanently closed.
-Normal network/API-module/protected-file/NN-after-close guard counters all0.
-Existing one-byte OS lease acquired by the original owned runner. No resume or retry.
-Native original52452 exited0 (ab1164), actual worker55812.
-CPU-only root recount nativecc4454 exited0, rehashing1,484 input files and212 committed output files, verifying journal/counters, per-frame detection and empty maps, saved trajectory scores and block selection. Checker Torch imports/model deserializations/NN calls0.

Detector: confidence0.35, NMS IoU0.5, image640, maxdet300; six cases on GPU0,175-frame/324-box large cohort on CPU. Six cases contain61 frames,58 scored and3 arena-only exclusions. Every18 included empty frame was independently recounted. One-to-one matching IoU0.5. Actual tracker/profile/resets/descriptors match frozen593; no reference boxes or identities seed the tracker.

Detection nonregression compares each case/session and every empty frame with original ares-v1.2.2. Trajectory nonregression compares each case with ares-v1.3.33. Control33 fast certain-longest coverage35/52=67.31%, measured matches47/52, maximum missed gap5 frames.

## Representative exclusion evidence
The table reports one concrete regression per model, not an exhaustive list.

| Model | Fast certain-longest | Fast measured matches | Max missed gap | Representative failure |
| --- | ---: | ---: | ---: | --- |
|118|65.38%|46/52|5|KFVZ FP0 to2|
|119|65.38%|46/52|5|KFVZ FP0 to3|
|120|57.69%|45/52|5|y5WmT7RSl4A session FP1 to9|
|121|65.38%|46/52|5|KFVZ FP0 to3|
|122|67.31%|47/52|5|B3QCzjTKDLs session FP10 to15|
|123|65.38%|46/52|5|KFVZ FP0 to3|
|124|65.38%|46/52|5|IWHH measured18 to17, certain14 to13, fragments0 to1, case gap0 to1|
|125|65.38%|46/52|5|B3QCzjTKDLs session FP10 to14|
|126|50.00%|42/52|5|KFVZ FP0 to3|
|127|61.54%|45/52|5|KFVZ FP0 to3|

124 passed the original-baseline detection gates but failed per-case trajectory nonregression. All other models failed a case/session detection gate. All ten retain a5-frame maximum missed gap across the fast cases. No candidate demonstrates stable trajectory improvement.

## Source review and evidence identities
One independent whole-packet review found0Critical/2Important. Before any actual NN evaluation, root reproduced and fixed both integration failures in one pass: canonical scorer/linker imports and omitted legacy CPU module bindings. Twelve local behavior tests and guarded actual13-module CPU import authentication passed. No rereview was performed; the root verified the fixes.

- Final packet SHA256:352c504f0bd2c298a41eaecef8ba41a936d28c7db253ffb60c10a859c0cf4245.
- Source release SHA256:eebd272995535c41f72ce3b5e05143079245dd92156480524e3f49e262dc3828.
- Runtime completion SHA256:643cd7bc19d42057102e4f769bc20ca8b4db9e0358ff2ab6cc971007bc3489d8.
- Independent root validation SHA256:30919420e8c33e6ef809e21e97eb98a034443e575925068b266b8e6df9b3ed32.

## Limits and next evidence
These are consumed development windows with source-only LLM references. Human/physical accuracy, full-video/live equivalence, three unused final sessions/300 frozen boxes and actual production weak-detection tracking remain unproved. New independent final groups0. No production merge/deployment, full-project test pass, default change, or live API-menu verification is claimed.

Jev was not used in these trainings. Existing Jev candidate/transport prototypes passed42 offline tests with synthetic images/fake transport; real Jev requests, uploaded frames and added Jev labels remain0. Its experimental image/Box quality on blurred Beyblades still needs a bounded calibrated pilot and controlled training comparison.

A separate offline inventory found89 root registry manifests. This is not a live API choice count; the requested maximum10 qualified choices including unchanged default still needs reconciliation. Old artifacts should be preserved, not silently deleted or relabeled as qualified.

This publication contains aggregate evidence only: no raw media, labels, private code, credentials, model bytes or full logs.
