# Jev image pilot615 and Laya suitability - 2026-10-22

A new user-supplied TypeSafe credential passed the installed Jev-desktop client's one synthetic-text doctor check: response model jev-1.14.0, choice preview,318input/31output tokens,258ms reported API latency. The key was supplied through previously verified hidden input, held only in process memory and never saved or disclosed. This single call is not a UI speed benchmark.

The manually authorized image pilot615 completed three real calls to the official TypeSafe image endpoint with TypeSafe-Danger-Zone-Images:true and pinned jev-1.14.0. All returned HTTP200. Inputs were three frozen, visually checked public YouTube TRAIN arena crops from SMb85H1izpg: overhead blurred top, empty arena, foreground blurred top. No private/protected/final-evaluation images, source paths/URLs or local reference boxes were included in request state.

Actual usage:2191input/246output tokens, zero unknown usage. Per-image request latency was0.485,0.329,0.359seconds. These are three samples, not a production benchmark. The prior614 image call returned403 with unknown usage; that immutable failed ledger is preserved.1prior+3new calls reaches the original4image-attempt cap. No automatic retry, ledger reset or access workaround occurred. The new credential was explicitly supplied by the user and verified before the new pilot.

Annotation result: all3 receipts were no_supported_candidate under the frozen presence threshold0.85 and Box-confidence threshold0.8. Both positive reference crops yielded no accepted box; the empty crop also yielded none. This shows an annotation-admission limitation despite successful API connectivity. It does not establish human-confirmed accuracy. The existing adapter did not retain raw probabilities/unused boxes for rejected candidates, so no post-hoc threshold calibration can be performed. No threshold was lowered, label auto-added, dataset changed or claimed trajectory improvement produced.

Source/scope review:0Critical/0Important/0Minor. Offline dry-run:3dry receipts,0APIcalls. Original live native session27909, launch52d61c, terminal8254be, exit0. Independent readback verified all3image hashes, packet/source hashes, exactly3success journal rows with usage, and unchanged prior614ledger.

Evidence SHA256:

- Packet:8473b9fe9cc1b4e633bfb6f79971c5406c1b31059269b32144a1db1e95f06d44
- Source review:a840ab1f84220524e403ac79ee1c1977c134e3b67bea4d268474919510f4d961
- Result:ab558acbac9e8a683722f2cacbd77f1e577a58a8ea18c19ba5352146ca96adb1
- Completed journal:9cf14a1dde448fd6fa9b2578398af5382914dc5f6b5941be30896f2caab5ebc4

The user also asked about local Laya. Local metadata reports0.3.6; its existing backend accepts textual prompts/typed questions and the cached English encoder is ModernBERT. The upstream project describes choice/score/noul decisions over text, not image Box localization. No Laya NN inference or upgrade was performed while the paired YOLO run131 was active. Laya may be evaluated for review-note categorization or annotation-work prioritization; it cannot provide independent image evidence through this installed interface. No Laya accuracy gain is claimed. Primary source: https://github.com/NandhaKishorM/laya

Jev training labels added:0. Laya training labels added:0. New independent final groups:0. Default/catalog unchanged. Full optimizer-run count remains130; this API pilot is not a full training run. Next diagnostics should preserve raw typed judgments on a frozen TRAIN calibration packet before candidate gating, then use reviewed data and the existing nonregression/trajectory gates for any model promotion.
