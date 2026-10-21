# 2026-10-21: joint four-scale training of experimental116 (583)

The owned worker completed 30 epochs normally. Experimental ares-v1.3.116 was selected from validation and remains unpublished to the local API. Fixed regression scoring has not yet run for116. This record does not establish X Dash improvement or stable accuracy.

## Actual execution and selection
- Worker PID53172, native handle96253, terminal2f0b33, exit0.
- 4,200 TRAIN tensor forwards (batches, not images),280 optimizer updates.
- 6,075 observed DetectionModel.__call__ roots across the worker. Direct constructor forward calls were not independently budgeted.
- Selected checkpoint order11, completed epoch12: VAL80TP/1FP/5FN on54 images/85 reference boxes.
- 23 of30 checkpoints met the unchanged VAL precision>=.98 gate. Selection maximized recall, then fewerFP, then earlier epoch. An independent arithmetic audit confirmed the selected row.
- Initial selected114 SHA: d1b0d7978483d69714a906f5c27df14ca7fe5d20a265bc7f1fdcf6b2cb445b3d.
- New116 weight SHA: 477c1ab1d6e1038a3c186c83488c5d9aba0e1f5750ac5a937a81dd93ac3f67b1.

VAL results are consumed LLM-label agreement used for checkpoint selection. They are not independent generalization evidence, a real-world accuracy estimate, or the fixed X Dash result.

## Recipe and data
The unchanged659-pair dataset contains558TRAIN/54VAL/47TEST,1,023 boxes and114 TRAIN negatives. This run added zero images, labels, videos or independent final groups. Historical15 hybrid TRAIN rows/30 boxes remain included; the total is not all independent source-only annotations. Source=llm,human_confirmed=false.

All four scales participated in full-head TAL assignment: strides4/8/16/32,34,000 anchors per640x640 input, stride floor8/topk10/alpha.5/beta6. Layer25 and all26.cv2/cv3 branches were trainable; all other parameters and buffers, including layers0..24 and DFL, were frozen. Original499 preservation was deliberately retired for this recipe.

Runtime checks verified379 frozen state entries live and after stock checkpoint serialization at each epoch. The independent checker audits those records and checkpoint hashes; it does not deserialize models to independently inspect tensors. Individual scales may have zero positives in a batch or epoch.

Seed42,30epochs,640,batch4,workers0,AMPfalse,warmup1,mosaic0,session-balanced sampling, checkpoint each epoch,patience30. Nominal LR.000005 was multiplied by100 only around the vendor optimizer step, giving effective initial base.0005; nominal rates were restored afterwards. Floored gamma2 background weighting and stock positive BCE were retained. Standard full-head validation loss and VAL-only selection were unchanged. No OOM retry, batch reduction, NaN rescue or fp16 clamping.

## Review, independent audit and preservation
One fresh whole-package review found C0/I1/M1. Root resolved both findings in one combined repair pass, with no rereview. The important repair chooses non-None EMA, otherwise model, in both initializer reads; the reference is checked before reconstruction. A mocked actual trainer-initializer-path test reproduced None.float() (nativee54fec exit1) and passed after repair (db054e exit0), with zero actual detector construction/forward/update. The minor correction limits budget wording to observed __call__ roots.

Before any NN execution, preparation had failed because an upstream output map omitted split_manifest.json. The finish-staging step verified all already-copied bytes against unchanged574 and exclusively added the separately pinned manifest. This was a pre-neural preparation correction, not an ML retry.

Independent stdlib checker: handle22893, terminal97a525, exit0, zero model calls. It rehashed2,649 training inputs and630 named executable sources; checked12 current own sources and17 named external source hashes, native ownership/argv/nonce/PID/stdout, all30 epochs,4,200 batch records,280 update records, per-head gradient/assignment records, sampler evidence and30 checkpoint hashes. Native binaries and the semantics of all sealed sources were not independently audited.

Private immutable evidence manifest:
bf572b98c2c9a426f2b87d605085853f17a6399edd241b966d0c62daab41ff92
(1,473 private files,1,371,168,671 bytes,1,965 external bindings; no raw artifacts uploaded.)
Source review: ff7efe4a9bc7f4623d711febbb4c75a31c078cade1f3b613200d30e6146310f1
Source release: ffc5dfc81d26fcc87ea37f9677d68cf29e008291a991ce3f74d60f2a72f8f36e

Shared training state and the existing one-NUL lock bytes were preserved. No local API publication, default change or cloud promotion occurred in583. Only a separately scored/reviewed116 may advance as an optional local API choice.

Final stable acceptance remains unmet: at least3 unused shooting sessions and300 source-onlyLLM boxes frozen before prediction; precision AND recall>=90% at confidence.35/one-to-one IoU.5, with per-session results, empty-frame false positives and exclusions. This run contributes zero independent final groups.
