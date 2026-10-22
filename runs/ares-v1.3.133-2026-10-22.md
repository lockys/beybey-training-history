# ares-v1.3.133 - 2026-10-22

Completed optimizer-backed full run 133: seed 44, blur arm of the paired 128..137 campaign. Total completed full optimizer runs: 133. Stable high-speed/blurred trajectory improvement remains unproven. No API publication, default change, or new Greek name.

The 659 image/label pairs remain split into 558 TRAIN, 54 VAL, and 47 TEST. The paired blur dataset replaces 89 positive and 23 empty TRAIN images while preserving labels and all holdouts. Training used 30 epochs, 640px, batch 4, AMP off, AdamW lr 5e-5, the stock three-scale 33 initializer, ordinary BatchNorm/BCE/TAL, and deterministic uniform sampling. Actual counts: 4,200 TRAIN forwards and 280 optimizer updates. All 30 periodic checkpoints were saved; no TEST inference, automatic retry, or OOM rescue.

The fixed 54-image/85-object VAL selection at confidence 0.35, one-to-one IoU 0.5, and precision floor 0.98 selected epoch 9 (epoch8.pt), SHA 7dbfd2d62caf12ee2b3f0a79691ad35245de27126037f78940c44f37c9ed873e: 83 TP / 1 FP / 2 FN. The seed-44 control 132 selected 82 / 1 / 3. All five VAL sessions have nondecreasing TP and nonincreasing FP relative to that control; the one additional TP is in youtube-pmEIYBfQYzQ. This is checkpoint-selection agreement against source-only LLM references (human_confirmed=false), not independent accuracy or trajectory evidence. No API eligibility follows from these VAL totals.

Runtime counters: 31 constructors, 1 fresh model, 66 loads, 6,068 observed registered roots, 4,200 TRAIN forwards, 280 optimizer updates, 1,620 VAL predicts, and 30 native backend setups. Network, API-import, protected-read, and outside-write guard counters were all zero. NN was permanently closed before completion.

Original worker: session 99188, launch chunk 4682e7, PID 69220, terminal chunk 17310a, exit 0. Independent CPU audit: session 35140, launch b02a96, terminal 8bef42, exit 0. It rehashed all 30 checkpoints, 5,301 inputs, and 630 executable sources with zero NN calls and validated original native identity and packet linkage.

Evidence SHA256:

- Root: d485a987583b8069ad6578d4c617d1ead61a636d4ac9ae6d1dc4cd53a41d015a
- Completion: 531297d468b8e86837c9155844c984f1ac7b0b1e96f1b03e496609c061f1aee6
- Native terminal: 37fb34a5842c85f8ca21619242169e9703209ed772c652827f5c874f76711380
- Native launch: 7a8e90f32d887a96e4fbf1d6684b7ce73cb06c529ef07eba3f3179c939648a41
- Plan: a5097b1440661d02fab39977a0f2a96891390bfbe67cd139b9143efea3157324
- Release: 744baec8fa28f280e7110361457c765d59b358cd0134fc2285d9be3fdff99e96

The installed local Laya 0.3.6 interface accepts text and typed decisions; the current upstream README likewise describes text choice/score/yes-no decisions, not image assets or Box localization (https://github.com/NandhaKishorM/laya). Code and metadata inspection performed; no Laya model inference or upgrade. It may help categorize written failure reviews or prioritize annotation after comparison with deterministic ranking, but no detector/trajectory gain has been demonstrated. Jev and Laya training labels added: zero. Jev raw diagnostic 618 retained low-confidence image judgments without lowering acceptance thresholds or adding labels.

CPU planning for the post-ten 128..137 comparison is recorded in preparation 619. No evaluation packet or NN admission has been released. Run 128's two-phase history must be validated separately from 612's nested run schema. The full fixed detector/trajectory gates, at least three unused final shooting sessions/300 frozen reference boxes, and real production consecutive weak-detection acceptance remain pending. New independent final groups: zero. Keep at most five genuinely eligible models per ten completed optimizer runs and at most ten API options including the unchanged default. No storage cleanup was performed; a separate exact old-epoch deletion proposal remains pending user approval. Shared legacy state unchanged.
