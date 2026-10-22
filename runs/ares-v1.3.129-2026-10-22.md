# ares-v1.3.129: paired mild-blur run; source-only contiguous frames

Date: 2026-10-22 (Asia/Taipei).

## Accounting and Jev status

Completed full optimizer runs:129 (previously128). This is run2 of the prespecified128-137 ten-run block. Remaining130-137 have not started.

Jev API calls:0. Jev-generated training labels:0. This run uses the existing LLM annotations; the separate Jev integration is an offline prototype and did not generate training labels or participate in this training.

## Paired training

- Seed42, balanced mild TRAIN-only motion-blur arm; control128 uses the same seed and initializer.
- Trusted three-scale model33:24 layers,strides8/16/32,nc1.
-659 pairs:558 TRAIN,54 VAL,47 TEST.89 positive and23 empty TRAIN images carry deterministic mild blur; labels and holdout images are unchanged. Source=llm,human_confirmed=false.
- Trainer source is byte-identical to control128.30 epochs,640,batch4,workers0,AMPfalse,AdamWlr5e-5,warmup1,mosaic0,stockBN/BCE/TAL and stock DFL freeze.
-140 actual TRAIN forwards per epoch,4,200 total;280 confirmed optimizer updates.
- All558 TRAIN samples occur exactly once per epoch. All30 checkpoint hashes, epoch samples, finite gradient/update evidence and registered root journal were rechecked.
- Retained predictor-clone registration is included; it changes monitoring after stock setup, not training/fusion math.
-27 focused pure/fake tests passed after the integration regression first reproduced the unregistered-clone failure. Fresh full16-source review found0 Critical,0 Important,0 Minor.
- Stage and final audit verified5,301 inputs and630 executable-source files.
- Worker guard counters: network0,API import0,protected read0,outside write0.

Original worker session32327, launch51a408, terminal5d60c7, exit0.
Independent CPU audit session19033, launchebc914, terminal203fb7, exit0; no neural calls.

Final operation counts: constructors31,fresh models1,checkpoint loads66,registered roots6,068,TRAIN forwards4,200,optimizer updates280,prediction calls1,620.30 retained native predictor setups were checked.

## VAL-only selection

The unchanged rule selects maximum recall at precision>=.98, then fewer FP and earlier epoch, across30 checkpoints on the same54 VAL images at640/conf.35/NMS IoU.5/match IoU.5.

| Arm | Selected epoch | TP | FP | FN |
|---|---:|---:|---:|---:|
|128 original control|1|81|1|4|
|129 mild blur|12|82|1|3|

The one additional match occurs in one validation session. These labels are LLM references used for checkpoint selection, not an independent accuracy or trajectory test. This does not establish that blur augmentation improves general performance.

Selected129 weight SHA-256:9948a50d9ade463b7b40e0bc2ce78b87fd15a44d4c48505ad06efb16584ef5e4.
API published:false. Default changed:false. Greek rename:false. Stable trajectory improvement proven:false.

## Source-only frame preparation613

One bounded three-query public metadata search produced0 usable new video URLs and0 downloads. This is not evidence that suitable footage does not exist.

Existing cached public sourceZ6Pjk7m5280 was inspected without model predictions. Two fixed16-frame contiguous windows were decoded at native1280x720:4012-4027 and28252-28267.2 existing exports were reused and30 new PNGs were saved. Known prior exports8 plus new30 gives38 accounted exports, with2 remaining under the existing40-frame source cap; the budget was not reset.

One new CPU decode pass processed28,268 frames in39.656 seconds. Both reused frames matched their prior decoded RGB hashes. A separate audit reopened all32 PNGs and recomputed32 file and32 RGB-pixel hashes. Network/neural-import/protected-read/outside-write counters were0.

Original source-only session73555, launch8d4845, terminal39b349, exit0. Source completion SHA-256:2cd1b58298cd787e51d0b7607514c89709a1ede8a7398fb9e502e53440bc6a55.
Plan SHA-256:22e0ff7b7dd030bab6f6730c40c924eb7824e12dabc439dd790e063601d13fc7.
Decoder SHA-256:f6b83697cac6d9daf4e92336b09eb13ebcc0b3cb2419c0e46893ebfef737a937.

Only6 native images have been visually inspected. Visible issues include rail blur, strong perspective, shallow focus and frame truncation. Encoded60fps does not establish original capture speed or real-time X Dash motion. Camera/session novelty relative to other edited footage remains unproved.

The source remains unassigned and barred from TRAIN, model inference and final acceptance. No boxes, empty references or scoring cohort were admitted. New independent final groups:0. These frames did not alter run129 inputs.

## Training proof digests

- Training plan:a5097b1440661d02fab39977a0f2a96891390bfbe67cd139b9143efea3157324.
- Reviewed source release:744baec8fa28f280e7110361457c765d59b358cd0134fc2285d9be3fdff99e96.
- Successful completion:a9b191844bcd1a82a165bd2e3481d631761c7531e92f984e2d0df7659ea3a077.
- Independent root validation:9ae154f6693b9d46b63840b05a78afb1d9261d365b5e171a60eec3210582b69d.

## Remaining work

Complete130-137, then apply the identical frozen detection/empty-frame/trajectory comparisons to the entire ten-run block. Per-case/session TP must not decrease, FP must not increase, and each empty frame's FP must not increase. Retain at most5 genuinely eligible candidates per10 completed optimizer runs, and at most10 API choices including the unchanged default. Missing comparable evidence excludes a candidate; do not force5 or10.

The independent final stable-trajectory gate and actual production weak-detection frontend verification remain unmet. No new API-eligible candidate is established by this report.

Only aggregate history was uploaded; no video/image pixels, labels, private source code, raw logs, credentials or weight binaries.
