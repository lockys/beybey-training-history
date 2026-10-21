# Fixed scoring of ares-v1.3.117 (batch 588)

Recorded on 2026-10-21. This is an exploratory regression result, not proof of stable improvement or human-verified accuracy.

## Candidate and lineage

The candidate is ares-v1.3.117, SHA-256 789ca723ad0dac108e07e10f046738d925fd67e9ec27b90ed42a112942d0bd21. It was selected from completed training587 by the unchanged VAL precision gate and ranking: order7 / completed epoch8, 81TP / 1FP / 4FN, among27 qualified candidates. That training completed30 epochs,4200 TRAIN tensor forwards,280 optimizer updates and6075 observed DetectionModel.__call__ roots. It trained the neck and four-scale Detect head while preserving241 frozen backbone/DFL state entries. Those tensor claims rely on reviewed runtime checks and sealed records, not a separate checkpoint tensor audit.

Closed training587 SHA-256: be68a80ab2f45ae8c0d3719f02d005eb6b0fec31517971731f581682ae78d020.
Closed scoring588 SHA-256: 16ba8707402c4b914bec5b767ed485cb54668fd43d88b9b04e62e16b79f4ff7d.

## Fixed evaluation

Native worker39620 completed once (terminal43729c, exit0); the independent saved-prediction checker completed605022/exit0 and closure completed f32b57/exit0. The worker used8 model loads,244 predictions and251 observed roots:175 CPU and69 GPU predictions,241 labelled frames and3 arena-only frames. Worker elapsed97.854856 seconds. No new training, optimizer update, API request or shared-state write occurred during scoring. Direct constructor forwards are not independently budgeted;488 is the conservative monitor ceiling,251 the exact observed success count.

The six evaluator helpers remained byte-identical to577 and584. Original332/333 reference pixels, boxes, cohort membership and qualification rules stayed fixed at confidence0.35, NMS0.5, image size640 and one-to-one IoU0.5. Five cached baselines110/113/114/115/116 were rehashed and their saved predictions recounted without baseline NN replay. Fourteen CPU receipts remained bound. A fresh whole-package review found0 Critical,0 Important and1 Minor; root corrected only the plan's attribution of cached comparison production. No rereview or NN rerun occurred. All actual worker observations were retained; the resource receipt was transcribed from its returned tool result.

## Results relative to LLM references

| Cohort | TP | FP | FN | Precision | Recall |
|---|---:|---:|---:|---:|---:|
| Fast-motion cases |45|2|7|95.7447%|86.5385%|
| All six cases |77|4|9|95.0617%|89.5349%|
| Large324-box cohort |322|28|2|92.0000%|99.3827%|

Large-cohort empty-frame FP:2. Original qualification:false.

Large-cohort sessions, TP/FP/FN:
- youtube-y5WmT7RSl4A:54/3/0.
- youtube-B3QCzjTKDLs:36/16/1.
- youtube-Iaoe6DA-680:144/0/0.
- youtube-Wm-TzWxswg8:88/9/1.

Compared with cached116, fast counts are unchanged. The six-case FP count falls5 to4. Large-cohort TP rises321 to322, FN falls3 to2, totalFP stays28 and emptyFP stays2. Session FP changes are -5,+3,0,+2 respectively; therefore per-session nonregression is false. The larger total does not prove that X Dash misses improved: the seven fast-case misses remain.

## Limits and publication state

These cohorts have already informed model development. New independent final shooting-session groups:0. Stable improvement remains unproven. Final acceptance still requires at least3 unused shooting sessions and300 source-only LLM boxes frozen before predictions, both precision and recall at least90%, with per-session results, empty-frame FP and exclusions. Human confirmation is not blocking; source=llm, human_confirmed=false, review_status=pending. Training's inherited15 hybrid rows/30 boxes must not be described as fully source-only labels.

At this recorded point117 had not been published as an API choice. Optional publication requires its separate review; no default or cloud promotion is claimed. The training587 history was published at commit1358074e768c923213d9d825689f0b2897e28c92 and its exact4328-byte payload was verified through immutable-commit readback.
