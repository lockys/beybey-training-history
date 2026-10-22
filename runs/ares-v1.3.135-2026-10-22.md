# ares-v1.3.135 - 2026-10-22

Completed version135, seed45 blur arm, after the user restored project write access. This is the **134th completed optimizer-backed full run**. Interrupted version134 remains incomplete, with its24complete epochs and consumed operations preserved; it was not resumed, restarted, or counted. Version numbers now differ from completed-run totals.

The new631 packet admits only the original never-started135/136/137 slots and explicitly resolves old project paths for reads. Frozen prior packets and shared state remain unchanged. Trainer, operation-budget contract and runtime are byte-identical to612. A fresh independent review found no Critical/Important issues and verified6,011 source/input/executable bindings. Thirty-two behavior tests passed in the original vision runtime; the five new relocation/handoff tests first failed against the missing behavior.

Training retained659 image/label pairs (558TRAIN/54VAL/47TEST), source-only LLM provenance, human_confirmed=false, stock three-scale33 initializer,30epochs,640px,batch4,workers0,AMPoff,AdamW lr5e-5 and the existing fixed mild TRAIN-only blur arm. Actual counts:4,200TRAIN forwards and280optimizer updates; all30periodic checkpoints saved. No TEST inference, automatic retry, counter reset or OOM rescue.

Fixed54-image/85-object VAL checkpoint selection at confidence0.35, IoU0.5 and precision floor0.98 selected epoch1 (epoch0.pt), SHA9fec3cfcf46053084a5811e50d38c874d959f981c12efe84582ec6027a5a4d3c:82TP/1FP/3FN. Version133 selected83/1/2. This is not a same-seed comparison, and seed45 has no completed control. No independent accuracy gain, stable trajectory improvement or API eligibility follows from these source-LLM selection counts. This model remains research-only.

Original worker:session38411, launch8be674, PID35932, terminal81c0ab, exit0. Independent CPU audit completed in native chunk1cbd7c, exit0; that immediate command returned no session ID. It rehashed30checkpoints,5,363inputs and630executables with zero NN calls. All runtime guard counters were zero. Budget counters:31constructors,1fresh model,66loads,6,068registered roots,4,200TRAIN forwards,280updates,1,620VAL predicts.

Evidence SHA-256:

- Root:9ea4a01e6f3598bfb7168810b0f23f9239ad538d816578b927cf8e1dbbf31bf9
- Completion:3fc57ebbb06e06d206fc4c3b7e0e9635bd30c62692e920ee40102236a20c607a
- Native terminal:ee8472a153dbede3395582989cda24f0e601a934a5ef371ddc0127ad2c3231a7
- Native launch:97954ba30da617cc2c97b4571d57a90685bdead1f8cc268823db50911c51c2a0
- Plan:4daa8c71b7b1ed54065e6abf963ee97beaa07e7db061e0dcc7917e4bcc08e57c
- Release:3882bbc723d5d0e653d084c6b91038102663470c0ceb916b751569e51c7e3396
- Review:0a69dc77b7723fdbf97e97c26a58992a215d74abbf5c455426800e1bd7ba5bbb

The original128..137 slot block can yield only9completed runs because134 is incomplete. Do not claim ten completed runs or five completed seed pairs. Retain the ten-actual-completions requirement before this block's selection evaluation, fixed per-case TP/FP and per-empty-frame gates, at most5eligible models per10completed runs, and at most10API choices including the default. Final acceptance still requires unused shooting sessions/frozen references and the real production consecutive weak-detection frontend.

Jev/Laya training labels added:0; new independent final groups:0. Existing Jev1.14 diagnostics were successful HTTP responses but admitted no labels; their closed request ledger and thresholds were preserved. Public-source metadata remains unassigned; one candidate has a prior closed access route and is excluded from further access. No new source media or reference boxes were added.

No API publication, default change or new Greek name. Authorized PNG deduplication remains unapplied: fresh synthetic hardlinks work, but full Windows audit-security information is unreadable without a missing privilege, and the old replacement prototype remains withdrawn. No training images or model weights were deleted.
