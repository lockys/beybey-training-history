# ares-v1.3.136 - 2026-10-22

Completed version 136, seed 46 control arm: **135 completed full optimizer training runs** in total. Interrupted version 134 remains incomplete and excluded. The original never-started slot was admitted through the reviewed 631 relocation/handoff packet; no previous attempt was restarted or given reset counters.

Training kept the stock three-scale 33 initializer, 659 image/label pairs (558 TRAIN, 54 VAL, 47 TEST), the control dataset, 30 epochs, 640px, batch 4, AMP off and AdamW lr 5e-5. References remain source-only LLM labels, human_confirmed=false. Actual evidence: 4,200 TRAIN forwards, 280 optimizer updates and all 30 periodic checkpoints. No TEST inference, OOM rescue or automatic retry.

Fixed VAL selection chose epoch 1, SHA 74c8b9564fc49deeb8faf192c83b2908d220759d1fa1fc126c0a19d21889dad3: **82 TP / 1 FP / 3 FN** on 54 frames and 85 reference objects. Version 135 has the same totals; version 133 has 83 / 1 / 2. These comparisons use different seeds and checkpoint-selection references. The paired seed-46 blur version 137 is not yet complete at this observation. No independent detection or trajectory improvement is established.

Original worker: session 31424, launch 4fc8f0, PID 25336, terminal bc4a36, exit 0. Independent CPU audit: session 80798, launch c380c5, terminal 8e5a15, exit 0. It rehashed all 30 checkpoints, 5,363 inputs and 630 executable files with zero NN calls. All runtime guard counters were zero. Counters: 31 constructors, 1 fresh model, 66 loads, 6,068 registered roots, 4,200 TRAIN forwards, 280 updates and 1,620 VAL predicts.

Evidence SHA-256:

- Root: 2bd836b34e0dd99827caa9baea95652773046aa412451b633b8243b48f8c6ed7
- Completion: d70910dbafd377321665b116c19d069f0ca92220488b053703ff170ad2648274
- Native terminal: 1ef1a8bef8a1e72f847768855c611d0c54797af2c467bf6bb7a591d954e8d915
- Native launch: cadcd5599521fa64d8bf7ca6a5368469450eb1d4499b2e642ddf25c28ab57c53
- Plan: 4daa8c71b7b1ed54065e6abf963ee97beaa07e7db061e0dcc7917e4bcc08e57c
- Release: 3882bbc723d5d0e653d084c6b91038102663470c0ceb916b751569e51c7e3396

The original ten-slot block has an incomplete slot and cannot be counted as ten completed runs. Preserve the ten-actual-completions requirement before selection evaluation, fixed-case TP/FP and per-empty-frame rules, at most five eligible candidates per ten completed runs and the total-ten API cap. The existing active-menu policy controls explicit model choices; registry artifact counts and the older shared-state snapshot do not establish the live menu.

Version 136 remains research-only: no API publication, default change or new Greek name. New independent final groups and Jev/Laya training labels remain zero. Stable high-speed blurred trajectories still require the unchanged independent-session and real production frontend gates. No training images or model weights were deleted, and shared state remains unchanged.
