# ares-v1.3.138 - 2026-10-22

Version138 completed a new seed47 control run: **137 full optimizer training runs completed overall**. The current block now contains ten actual completions:128-133 and135-138. Interrupted134 remains incomplete and excluded. Version128's failed training pipeline plus selection-only recovery counts as one optimizer run. This block has four complete control/blur pairs, with unmatched45blur and47control; it is not five complete pairs.

Training reused the immutable631 datasets and stock three-scale33 initializer:659 image/label pairs (558 TRAIN,54 VAL,47 TEST),30 epochs,640px,batch4,AMP false,AdamW lr5e-5. Actual execution recorded4,200 TRAIN forwards,280 optimizer updates and30 periodic checkpoints. No TEST inference, automatic retry or OOM rescue. References remain source-only LLM labels, human_confirmed=false; accepted Jev/Laya training labels remain zero.

Fixed VAL selection chose **epoch2**, SHA0c4b3e9ceec00cac970a8e62ac741a5225132f8a302afa1b9627477e04c36057: **82 TP / 1 FP / 3 FN** on54 frames and85 reference objects. This is checkpoint-selection evidence. There is no paired seed47 blur run and no independent detection or trajectory improvement established by these counts.

Original native worker:session61226,launch479b4f,PID32812,terminal0f63e2,exit0. Independent CPU audit:session96952,launch005f16,terminal9d7744,exit0. The audit rehashed30 checkpoints,5,586 inputs and45,132 executable/runtime files with zero NN calls. The expanded dependency manifest includes existing bytecode/native files in the exact vision venv and base Python runtime; Windows OS and the installed GPU driver remain the trusted platform boundary. All runtime guard counters were zero. Execution counts:31 constructors,1 fresh model,66 loads,6,068 registered roots,4,200 TRAIN forwards,280 updates and1,620 VAL predicts.

Evidence SHA-256:

- Root:800eeb0c674ecb480a08c671611c88704edd3de9be992210a10c55bc768171c1
- Completion:d890d3175cc3f60e296cb1eea6c7b648e85b38bc1cabcf341ed10b055e58b96d
- Native terminal:3eb6fadaeb6f204de0e8fbbad4c09259a9841ebc3b41cfe45c8e72960140122c
- Native launch:e4ae24472c8be03054e3548cf5463c3f18a8a77a8f5d9c1e0061d4ce9ef7ee50
- Plan:fb50fd16ddb4917f00c98b868a40cd8753ac5c0422485acc2a30ae864dcb39f4
- Release:4702c48098d12af1f195d5e23e32c191483ffc452354c3683f30f1f11624e2bc

The CPU-only640 adapter validated all ten current histories and selected-copy hashes, including the128 two-phase lineage. Complete inventory SHA82ddb3728ea720217eb7b1b472bb6eac6c511143265f7a6e6c4e075491694d6d. This permits preparing a separately reviewed evaluation packet; it does not admit NN evaluation or establish API eligibility.

Preserve fixed per-case/session TP nondecrease, FP nonincrease and each empty-frame FP nonincrease; at most five eligible models from the block, and at most ten API choices including the unchanged default. Missing comparable evidence excludes a model. No API publication, default change, new Greek name or model/image deletion occurred. Stable high-speed blurred trajectories still require the unchanged independent-session and real production frontend gates; new independent final groups remain zero.
