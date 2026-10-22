# ares-v1.3.137 - 2026-10-22

Completed version 137, seed 46 blur arm: **136 completed full optimizer training runs** in total. Interrupted version 134 remains incomplete and excluded. This was an original never-started slot admitted through the reviewed 631 relocation/handoff packet; no earlier attempt was restarted or given reset counters.

Training retained the stock three-scale 33 initializer and the paired control/blur datasets with 659 image/label pairs (558 TRAIN, 54 VAL, 47 TEST). The blur arm changes 89 positive and 23 empty TRAIN frames. Settings remained 30 epochs, 640px, batch 4, AMP off and AdamW lr 5e-5. References are source-only LLM labels, human_confirmed=false. Actual evidence: 4,200 TRAIN forwards, 280 optimizer updates and all 30 periodic checkpoints. No TEST inference, OOM rescue or automatic retry.

Fixed VAL selection chose epoch 1, SHA 228b556a442fd70ca3b3be5b07ba3e78a9a4a4e3ea7dfb1abb808f125fc72261: **82 TP / 1 FP / 3 FN** on 54 frames and 85 reference objects. Paired seed-46 control version 136 has identical TP/FP/FN totals in all five VAL sessions. This is checkpoint-selection evidence and establishes no independent detection or trajectory improvement.

Original worker: session 41121, launch e94b10, PID 35536, terminal 2f4bcb, exit 0. Independent CPU audit completed in native chunk 3c27bb, exit 0; this immediate command was not assigned a session ID. It rehashed all 30 checkpoints, 5,363 inputs and 630 executable files with zero NN calls. All runtime guard counters were zero. Counters: 31 constructors, 1 fresh model, 66 loads, 6,068 registered roots, 4,200 TRAIN forwards, 280 updates and 1,620 VAL predicts.

Evidence SHA-256:

- Root: 7b4499db20c63155bb56601a02c6b60a166df367dd1ed756d6a43f912ddd7e0c
- Completion: e0499ae4bd7917f8aa5097a0a544c49b516099b1f67e1492e11d441c4343fdad
- Native terminal: 3c91dc1c2ed2523ea4a16b9d86a70c2318b2e5260a74e8137b34773df37edc30
- Native launch: 2f528c0eb3eea7d51ab8087a775af42224aac2890bc880a1bbaa3af3e9279078
- Plan: 4daa8c71b7b1ed54065e6abf963ee97beaa07e7db061e0dcc7917e4bcc08e57c
- Release: 3882bbc723d5d0e653d084c6b91038102663470c0ceb916b751569e51c7e3396

Slots 128 through 137 contain nine actual completed runs because version 134 is incomplete. Do not count this as ten completions or five complete pairs. Preserve the ten-actual-completions requirement before selection evaluation, fixed-case TP/FP and per-empty-frame rules, at most five eligible candidates per ten completed runs and the total-ten API cap. The explicit active-menu policy controls model choices; registry artifact counts and the older shared-state snapshot do not establish the live menu.

Version 137 remains research-only: no API publication, default change or new Greek name. New independent final groups and Jev/Laya training labels remain zero. Stable high-speed blurred trajectories still require the unchanged independent-session and real production frontend gates. No training images or model weights were deleted, and shared state remains unchanged.
