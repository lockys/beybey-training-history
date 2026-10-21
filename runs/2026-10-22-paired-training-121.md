# Paired training121: frozen-attention seed43 control

Date:2026-10-22 Asia/Taipei. Campaign596 real completed runs:4/10.
Goal remains active: stable fast/motion-blurred Beyblade trajectories.

## Actual training and selection

ares-v1.3.121,seed43,freeze11: backbone0..10 and DFL frozen; neck and detection
heads trainable. Attention10 stays frozen. Same common initializer117 and same
659pairs(558TRAIN/54VAL/47TEST),30epochs,batch4,640px,AMPfalse,AdamW.
This is the paired control for120(seed43,attention+neck+heads).

Actual169trainable parameter tensors,241frozen state entries, feature modules
13,16,17,19,20,22,25.30epochs/4200actualTRAINforwards/280actualoptimizerupdates/
6075observed DetectionModel call roots. Direct constructor-forward bypass is
disclosed;6075 is not an exhaustive universal neural-operation counter.
Original native owned process exited0, worker70888/launcher49452 distinct,
attributed via matching nonce activation and redirected output. No independent
kernel-parentage verification. No retry,resume,restart or concurrent second run.

Selected order13,the fourteenth epoch, among29qualified VALcheckpoints.
Selected weight SHA256:e47d7984cbf15785d0e32c0217e95887151596da9037395f43e9558f5c8262cb.

## Fixed VAL evidence

54frames/85LLMboxes,confidence.35,NMS.5,one-to-oneIoU.5:
TP82,FP1,FN3,precision98.80%,recall96.47%.

Per-session TP/FP/FN:
- mI4qN8iV0h0:23/0/0
- gTx9as_nf10:12/0/0
- X8Ab_zjm5H0:19/0/1
- shark-event:3/1/1
- pmEIYBfQYzQ:25/0/1

Actual source-record comparison with initializer117(81/1/4) shows pmEIYBfQYzQ
gains1TP/removes1FN, all other sessions unchanged, no VALsessionFP increase.
Run120 has the same82/1/3 aggregate but different errors: it improves shark while
adding a gTxFP. Aggregate equality therefore does not imply equal session behavior.

These are training-selected LLM VALresults. They do not establish independent
accuracy, fast-case improvement or stable trajectories. No fast/six/324-cohort
or identity-aware trajectory evaluation has run for121. No API admission.

Stock selected CSVrow14: mAP50 .98053,mAP50-95 .71089,precision .98641,
recall .94118. These confidence-sweep metrics use a different operating point
from the fixed.35/NMS.5 counts above. human_confirmed=false,review_status=pending.

## Execution evidence

Completion SHA256:804d5c30239cb69c84f0e3abb4889d95e825f87fd4927e9b6ae9fc02e34c2316.
Independent root-validation SHA256:1dfea1880d94c03332c7d93c2c47aa1268bb3e4d18db45204a763d60aa091c2d.
Reviewed source release SHA256:8b7fa95df7199a7854757a0395e7b229525fa4fd1210407025a465936999abf2.
Native terminale077cdexit0; stdlib checker4c038b ->af3d63exit0.
It rehashed2657inputs,630executables,13sources,30checkpoints; verified recorded
feature/head gradients, assignment, LRrestoration and independently recomputed
VALselection.0models loaded/0Torch imports/0NNcalls. Runtime checks support
frozen tensor equality; the checker does not independently deserialize tensors.

## Remaining work and policy preparation

Complete all ten prespecified actual runs, then rank using frozen596 trajectory
rules and original per-case/session/each-empty-frame detection nonregression.
Retain up to five actually eligible candidates, fewer if fewer qualify. API cap
remains ten total including unchanged default. No default, shared-state, model
menu, Greek name or immutable model-ID change occurred. New final groups0.

A separate offline numeric selection library passed27synthetic behavior tests
after one fresh source-only review and one fix pass for contradictory missed-gap
summaries. It cannot authenticate files, prove real training, publish a model or
replace missing per-frame evidence. Fixture runs are not actual training runs.
No new model predictions, Jev requests, media exports or labels came from it.

Stable acceptance still requires at least3unused shooting sessions and300
source-onlyLLMboxes frozen before predictions, both P/R>=90%, session/empty/
exclusion evidence and real consecutive low-confidence production tracking.
Existing consumed short windows do not satisfy that final acceptance.

Only aggregate history text is published: no raw media, labels, weights, private
paths, code, credentials or full logs.
