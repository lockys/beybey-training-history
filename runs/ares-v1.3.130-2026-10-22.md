# ares-v1.3.130 - 2026-10-22

Completed optimizer-backed full training run130: seed43, stock control arm in the fixed paired control/blur campaign128..137. This is the130th completed full optimizer run. Stable high-speed/blurred trajectory improvement remains unproven, and no weight was added to the API or given a new Greek name.

Training used the same659 image/label pairs:558 TRAIN,54 VAL and47 TEST. There were30 completed epochs,4200 actual TRAIN forwards and280 confirmed AdamW optimizer updates. The initializer remains the audited stock three-scale ares-v1.3.33. Image size640, batch4, lr5e-5, AMP off, all model parameters except stock DFL trainable, ordinary BatchNorm/BCE/TAL, deterministic uniform sampling and no TEST inference. This control arm has no experimental blur replacement. Labels remain source-only LLM references, human_confirmed=false; zero Jev labels were used.

All30 epoch checkpoints were evaluated on the fixed54-image VAL selection set at confidence0.35, one-to-one match IoU0.5 and selection precision floor0.98. Selected epoch3, SHA256 fa2ff7015b052ced1fb5757d02467d9d2446c5f7631d2afd72f11c78ecfb4145:82TP,1FP,3FN against85 LLM reference objects. These are checkpoint-selection agreement counts, not human-confirmed accuracy, independent final evaluation or trajectory improvement. No TRAIN/TEST sample was used for selection.

Per-session VAL selection counts (TP/FP/FN):

- youtube-mI4qN8iV0h0:23/0/0
- shark-event:3/1/1
- youtube-gTx9as_nf10:12/0/0
- youtube-X8Ab_zjm5H0:20/0/0
- youtube-pmEIYBfQYzQ:24/0/2

Actual execution counters:31 constructors,1 fresh model,66 loads,6068 observed roots,4200 TRAIN forwards,280 optimizer updates and1620 VAL predictions;30 native backend setups. Network/API-import/protected-read/outside-write training guards all remained zero. No OOM fallback, CPU rescue or automatic failed-slot restart was used.

Original native worker session68951, launch bf4ea2, PID70924, terminal745824, exit0. An independent CPU-only auditor rehashed30 checkpoints,5301 inputs and630 executable files; original auditor session50850, launch f0ebc6, terminal d92fad, exit0. Its neural calls were zero. Packet linkage and original native identity/hash chain passed.

Evidence SHA256:

- Root validation:fa66794d379d8261f43378ad3293d8e371728954af3ce739e87211e99b8a56a7
- Completion:d2810a1a607db3dd2a9cb526f09d3e0eec20e155bea0f9af54799545e1cfa12f
- Native terminal:1d0572ef3f31748a69366033494cc1459373b95d0f15506ce5f726f755dd7eb7
- Native launch:a9eaa5935c865f7197fe64314aa608a1675ac04350a8f8553b22abb27db96e8e
- Training plan:a5097b1440661d02fab39977a0f2a96891390bfbe67cd139b9143efea3157324
- Source release:744baec8fa28f280e7110361457c765d59b358cd0134fc2285d9be3fdff99e96

Separately, the real Jev image pilot614 returned HTTP403 on its first call; zero annotations entered training. At the user's request, the installed Windows Jev-desktop client's single synthetic-text doctor check also returned TYPESAFE_HTTP_403. The supplied Linux configuration path was absent on this host; offline doctor found the existing Windows user-environment credential without displaying it. The exact rejection cause and successful image quality remain unverified. No denied request was replayed and no access-control workaround was used.

New independent final shooting groups:0. The required>=3 unused sessions and>=300 source-only boxes are still absent. API eligibility must use the unchanged fixed per-case/session TP/FP and per-empty-frame nonregression gates plus trajectory/final evidence; missing comparable evidence excludes a version. Latest prior completed ten-run evaluation retained zero eligible candidates. API maximum10 including unchanged default, at most5 genuinely eligible per10 full runs, never fill by quota. This run's full-block evaluation is pending; the shared legacy state and API default remain unchanged.
