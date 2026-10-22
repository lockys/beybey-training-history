# ares-v1.3.128: completed optimizer run and separate selection recovery

Date: 2026-10-22 (Asia/Taipei).

## Accounting

Completed full optimizer runs: 128 (previously 127). This is the first completed run of the next prespecified ten-run comparison block.

Run128 executed one30-epoch optimizer training. Its original process exited1 after training, during checkpoint selection. A separately sealed selection-only process exited0 and an independent post-terminal CPU audit verified both phases. The same optimizer run is counted once; no training replay or extra optimizer run is counted.

The original failed packet, terminal, journal and weights remain preserved. Shared state, default model and API catalog were not changed.

## Optimizer training: batch610

- Seed42; original-image control arm; existing three-scale model33 initializer.
-659 image/label pairs:558 TRAIN,54 VAL,47 TEST. Labels retain source=llm and human_confirmed=false.
-30 epochs;140 actual TRAIN forwards per epoch;4,200 total TRAIN forwards.
-280 confirmed optimizer updates with finite nonzero gradient evidence.
- All30 epochs sampled each of the558 training images exactly once. All30 saved checkpoint hashes and update/root journals were independently rechecked.
- Original owned native session47634, terminal06d041, exit1.
- Failure occurred at the first checkpoint-selection predictor warmup: the vendor BasePredictor copies the loaded model, and the retained clone was not registered by the observer. The guard stopped that unknown root before its forward.
- Original guard counters: network0, API import0, protected read0, outside write0.

## Selection-only completion: batch611

The observer now admits only a retained exact native backend clone created from an already admitted DetectionModel. It calls stock setup, checks exact native backend classes, and registers the retained root before warmup. Unknown input roots and backend setup31 remain rejected. Normal copying, fusion and inference math are preserved; reporting-only model-info profiling remains disabled.

The one-shot recovery allows only the30 exact hashed epoch checkpoints and the fixed54 original control VAL frames at640/confidence.35/NMS IoU.5/match IoU.5. Optimizer construction, backward, TRAIN mode and fresh model construction are prohibited. No TEST/final inference is performed.

-1,620 new prediction calls;1,650 new registered inference root entries.
-0 new training forwards and0 new optimizer updates.
- All prior operation usage retained, including the closed609 constructor/load.
- Final cumulative usage: constructors33, fresh models1, checkpoint loads67, registered roots6,068, TRAIN forwards4,200, optimizer updates280, prediction calls1,621.
- Network/API/protected-read/outside-write and forbidden-training attempt counters all0.
- Original owned recovery session3726, terminal8391c3, exit0.
- Independent CPU audit session51343, terminalfc3daf, exit0; no Torch/model forward.

Fresh source review found0 Critical,1 Important,1 Minor. Root fixed the prospective activation/launch/finished-run packet-and-release binding gap and explicit640 report check in one pass, then resealed. Synthetic stale packet/release/run rejection tests showed7 failures before the fix. The retained-clone regression suite showed6 failures before its fix. All16 focused pure/fake tests subsequently passed. These tests do not prove GPU correctness; actual recovery and the post-terminal audit provide separate execution evidence.

## VAL-only selected candidate

- Selected checkpoint: epoch1 (zero-based epoch0.pt).
- SHA-256:7602a202bc5da8cefd7723d5449f36eaa4bb6c0036b4ebf053e272434cd7f9fc.
-54 fixed VAL images,85 LLM reference objects: TP81,FP1,FN4.
- Selection retained the existing maximum-recall policy with precision>=.98, then fewer FP and earlier epoch.
- This is agreement with LLM validation labels used for selection, not independent test or human-confirmed accuracy.
- API published:false; default changed:false; stable trajectory improvement proven:false.
- No Jev API request was used for this training or recovery.

## Proof digests

- Recovery packet:209d7f4f87ef410bfb289b285870749d6f50d0507e9e0f1e764649acb5709269.
- Reviewed source release:14e34e1aeac6a8c9db4299a19eb9d4d774308bc29e31d86375112a2b90602dee.
- Normal recovery completion:f8f34546fbffe7ffbbc4f3b17571368082307c4db9661842ac0448255a148b29.
- Independent root validation:2047834db4950269c0f78d2f5f75abd2d6e150d445f4062356b5fd0555a130ee.

## Remaining gates

The paired blur run129 has not started. The rest of the ten-run block and identical fixed detection/empty-frame/trajectory comparisons remain outstanding. No new independent final shooting group was added.

No new weight is API eligible from this report. Existing per-case/session TP-nondecrease, FP-nonincrease and per-empty-frame FP-nonincrease gates remain mandatory; missing comparable evidence excludes a candidate. At most five genuinely eligible choices may be retained per ten completed optimizer runs, with at most ten API choices including the unchanged default. No Greek rename or stable-improvement claim is made.

Only aggregate history was uploaded: no media, labels, private source code, raw logs, credentials or weight binaries.
