# Paired training 119: frozen attention control

Date: 2026-10-22 Asia/Taipei. Campaign596 real completed runs: 2/10.
Goal remains active: improve fast, motion-blurred Beyblade trajectories.

## Actual training and selection

- Model: ares-v1.3.119; seed42;30epochs;batch4;640px;AMPfalse;AdamW.
- Same common initializer117, same659 pairs:558TRAIN/54VAL/47TEST.
- Only paired factor: freeze11 (backbone0..10 and DFL frozen), neck and detection heads trainable. Attention10 remains frozen. Run118 used freeze10.
- Actual169 trainable parameter tensors;241 frozen state entries.
- 4200 actual TRAIN forwards;280 actual optimizer updates;6075 observed DetectionModel call roots.
- Direct constructor-forward instrumentation limitation remains:6075 is not a universal neural-operation counter.
- Original owned native process exited0; worker26512 and launcher53728 are distinct identities supported by matching-nonce activation and redirected output. No independent kernel-parentage claim.
- All30 checkpoint hashes verified; per-feature/head gradients, assignment events, learning-rate restoration and selection records audited by a stdlib-only checker with0 model loads/0 neural calls.
- Frozen tensor equality is supported by reviewed runtime checks. The checker does not independently deserialize checkpoint tensors.
- Selected order12, the thirteenth epoch, among27 qualified VAL checkpoints.
- Selected weight SHA256: 9af62be431dcd529c5b874624916a6df183876a97f83c35b3997fc851ca26222.

At fixed confidence.35, NMS.5, one-to-one IoU.5 on54 VALframes/85 LLM boxes:
TP81,FP1,FN4;precision98.78%,recall95.29%.
The common initializer117 has the same81/1/4 on this VAL cohort. Run118 has80/1/5.
This does not demonstrate trajectory improvement.

Per-session TP/FP/FN:
- mI4qN8iV0h0:23/0/0
- gTx9as_nf10:12/0/0
- X8Ab_zjm5H0:19/0/1
- shark-event:3/1/1
- pmEIYBfQYzQ:24/0/2

Stock validator CSV at selected row13: mAP50 .97661,mAP50-95 .70231,
precision .98777,recall .95028. These confidence-sweep results use a different
operating point from the fixed.35/NMS.5 selection counts above.

## Evidence and limits

Completion SHA256: b0d861e7c3bee8faecd7a14dceaf58e63f26c6e351e76f2c4a560e9f9a332b68.
Independent root-validation SHA256: 9c654f4a8919986413fe70e67f32372194d8989a2b52e6fa8cda2245270a1ce0.
Reviewed release SHA256:8b7fa95df7199a7854757a0395e7b229525fa4fd1210407025a465936999abf2.
The audit rehashed2657 training inputs,630 executable inputs and13 packet sources.
Native terminal a5149f exit0; native checker a2d7e5 ->49c325 exit0.
No resume, restart, retry or concurrent second training occurred.

No fast/six/324-cohort or trajectory scoring has yet been performed for119.
Labels remain LLM-derived, human_confirmed=false and review pending; no new
independent final groups were created. Physical or stable accuracy is unproven.

After ten completed real runs, rank and admit up to five better candidates only
if all original fixed case/session TP/FP and empty-frame nonregression gates pass.
Keep at most ten API choices including the unchanged default. No119 API admission,
default replacement, Greek rename, gateway restart or shared-state change here.

Jev assistance remains an offline experiment, with no real Jev request, private
frame export or added training labels. Synthetic transport tests are not model
quality or actual training results.

Only this aggregate history text is published. No source video, raw labels,
weights, private paths, code, credentials or full logs are uploaded.
