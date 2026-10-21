# 2026-10-21: four-scale raw candidate diagnostic (582)

This is a diagnostic on two previously consumed frames, not a new accuracy cohort or proof of stable improvement. Frozen LLM references were kept unchanged; source=llm, human_confirmed=false. No frames or labels were added to training.

## Executed and independently checked
- Actual owned GPU worker: native terminal061606, exit0, PID67900;2 selected model loads,8 completed predicts,10 observed DetectionModel roots (including2 warmups).
- Independent stdlib checker: native terminal77a96c, exit0; no model calls. All4 original confidence.35 controls reproduced.
- Raw predictions had20400 anchors per frame,384x640 input and strides4/8/16/32. The.35 and.01 runs had identical raw tensors within each model/frame.
- Raw outputs at strides8/16/32 were exactly identical between114 and115. Only P2 differed, consistent with their frozen old-head recipe.

## Two targets, not an aggregate accuracy score

Highest confidence among raw boxes with target IoU>=.5:

| Model | Target | Confidence | Stride | Raw target IoU | Best retained target IoU at.35 | At.01 |
|---|---|---:|---:|---:|---:|---:|
|114|fast frame452|.002565889|16|.567514414|0|.436165309|
|115|fast frame452|.018718418|4|.504852147|0|.457186597|
|114|rail frame869|.340721428|4|.522543268|.476445926|.476445926|
|115|rail frame869|.553952813|4|.515079696|.476445926|.476445926|

None of the four model/target combinations retained a target box meeting the frozen IoU.5 rule at either threshold. Rail frame869 does contain a high-confidence object detection; it fails the reference-box overlap rule rather than producing no object output.

For115 on rail frame869, the retained stride16 box scored.768197298 with target IoU.476445926. It overlapped the adequate P2 candidate at input-space IoU.854405614. For115 on fast frame452 at.01, the retained stride8 box scored.067985892, target IoU.457186597, and overlapped the adequate P2 candidate at input-space IoU.865645743.

These score/overlap observations are consistent with greedy NMS/ranking. They do not replay a unique suppressor or prove a causal training fix. The two representative frames do not establish the cause of every historical miss.

## Next hypothesis and preservation
Joint full-head assignment and fine tuning is justified as the next experiment. Merely lowering confidence or enabling gradients without removing P2-only loss slicing is insufficient for these observed cases. No scoring threshold, NMS setting or reference box was changed here.

Training epochs, optimizer updates, new exports, network/API requests and new independent final groups were all0. Shared training state and the existing one-NUL lock contents were preserved. No new weight or API choice was published by582; previously selectable115 remains experimental and the default was unchanged.

One fresh whole-package review: critical0/important0/minor1;0 root repair passes,0 rereviews. The deferred minor concerns inherited batch-label wording, not runtime identity. The package sealed15 own sources,11 named external source files,70 inputs and630 named executable sources. The executable map comprises575 prior entries plus55 legacy support entries; native binaries are not independently sealed.

Private immutable evidence manifest:
7dd3d3f3fabd24426cf7ade99b115482c1bd2440b6763237e6885e1733a83b7c
(80 files,85,256,210 bytes,702 external bindings; raw evidence remains local.)
Source release:1116b9a1584d4d0d753d2961380795c7f32afd2bf8d00d76f023d998ce14e591
Independent validation:49f67b6c3e2fc2b45039045d9cd818fcf65081a51fc1a4a63a20e3005c7358e4

Stable acceptance remains unproved: at least3 unused shooting sessions and300 source-only LLM boxes frozen before prediction, precision AND recall>=90% at confidence.35/one-to-one IoU.5, with per-session results, empty-frame false positives and exclusions. Consumed regressions and these two diagnostics provide no new final-cohort credit.
