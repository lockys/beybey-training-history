# Paired training 120: attention plus neck, seed43

Date: 2026-10-22 Asia/Taipei. Campaign596 real completed runs:3/10.
Goal remains active: stable trajectories for fast, motion-blurred Beyblades.

## Actual training

Model ares-v1.3.120, seed43, freeze10: backbone0..9 and DFL frozen;
attention10, neck and detection heads trainable. Same common initializer117,
same659pairs (558TRAIN/54VAL/47TEST),30epochs,batch4,640px,AMPfalse,AdamW.
The paired seed43 freeze11 control121 is a separate next run.

Actual190 trainable parameter tensors,199 frozen state entries; feature modules
10,13,16,17,19,20,22,25.30epochs,4200actual TRAIN forwards,280actual optimizer
updates,6075observed DetectionModel call roots. Direct constructor-forward bypass
is disclosed: this is not an exhaustive universal neural-operation count.
Original owned process exited0; worker12460 and launcher56676 are distinct,
matching nonce activation and redirected output support attribution. Independent
kernel parentage was not verified. No retry, resume or restart.

## Fixed VAL selection and limits

28qualified checkpoints of30. Selected order3, the fourth epoch.
At confidence.35,NMS.5,one-to-oneIoU.5,54frames/85LLMboxes:
TP82,FP1,FN3,precision98.80%,recall96.47%.
Common initializer117 has81/1/4. This is one more VAL TP at the same aggregateFP,
but errors moved across sessions, so it is not per-session nonregression proof.

Per-session TP/FP/FN:
- mI4qN8iV0h0:23/0/0
- gTx9as_nf10:12/1/0
- X8Ab_zjm5H0:19/0/1
- shark-event:4/0/0
- pmEIYBfQYzQ:24/0/2

Compared with117, shark gains1TP/removes1FP, while gTx gains1FP.
No fast/six/324-cohort or identity-aware trajectory scoring has run for120.
No API admission, Greek rename or stable-improvement claim follows from VAL.

Stock selected CSV row4: mAP50 .97499,mAP50-95 .68976,precision .98573,
recall .92941. These confidence-sweep metrics use a different operating point
from the fixed.35/NMS.5 counts above. Labels are LLM-derived,
human_confirmed=false,review_status=pending; these are not physical accuracy.

## Evidence

Selected weight SHA256:400dc09e8f0a523e4699360c8a3637f8e7af4cb4e8b8b44f3b0cfd6b12398c29.
Completion SHA256:ee2ba3a42f4a84ba15f13de2e38457b617403565d69a91953c6f928877de3aca.
Independent root-validation SHA256:ad54558ccee3ad6ec84aea75d0c598a5bcd774e5100696f44a66148f58ab1787.
Reviewed source release SHA256:8b7fa95df7199a7854757a0395e7b229525fa4fd1210407025a465936999abf2.
Native terminalba8255exit0; independent checkerf5c18b ->8d7bc7exit0.
The stdlib checker rehashed2657inputs,630executables,13sources and30checkpoint
files; audited gradients, assignment and LR-restoration records; independently
recomputed VAL choice. It loaded0models and made0NNcalls. Frozen tensor equality
is supported by reviewed runtime checks, not independent checker deserialization.

## Remaining work

Complete the prespecified ten real runs, then rank by the frozen trajectory
metrics and retain up to five actually eligible candidates. Require all original
six-case/session/each-empty-frame and324-box nonregression gates plus no trajectory
regression vs33; preserve at most ten API choices including unchanged default.
Shared state and default remain unchanged. New independent final groups0.

A new bounded Commons source acquisition stopped at DNS resolution before HTTP;
no media bytes, decoded frames or labels were added and no alternate route/retry
was attempted. Source screening and audit work are not completed training runs.
Read-only evaluation preparation also identified that the old scorer's qualified
flag contains an extra web-sample gate; it cannot replace596's frozen rules.

Stable acceptance still needs at least3unused shooting sessions and300source-only
LLMboxes frozen before predictions, P/R>=90%, per-session/empty/exclusion evidence
and real consecutive low-confidence production tracking. No actual Jev requests,
private frame export or Jev-derived training additions occurred.

Only aggregate history text is published, without raw media, labels, weights,
private paths, credentials, code or full logs.
