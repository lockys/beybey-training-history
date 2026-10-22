# Jev native TRAIN image pilot648: stopped after first attempt

**Result: zero accepted candidates and zero new Jev training labels.** The original bounded pilot stopped on its first attempted request and was not retried. A valid response with accountable usage was not committed; the precise failure cause and HTTP status are unavailable. This is not evidence of model accuracy.

The packet allowed up to three new public TRAIN-only native PNGs: two frames with two physical tops from KHbDA9kOJho, and an empty arena with a fixed motor mechanism from u-EjRUhMuCc. All were existing TRAIN sessions; no new independent final session was introduced. Four local Codex LLM reference boxes were frozen and visually cross-reviewed before the attempt. Their coordinates were not included in the API request.

The existing image client was configured for jev-1.14.0 and the required TypeSafe-Danger-Zone-Images header. No returned-model or provider inference-latency claim can be made. The reviewed controls allowed one request per image, at most three new attempts, no retry, one in flight and a retrospective20,000-input-token stop. The prior seven recorded image attempts carried forward; the observed cumulative count is eight.

| Evidence | Observed |
| --- | --- |
| Original native terminal | bfbf9a, exit1 |
| New durable attempts | 1 |
| Known input tokens | 0; usage unavailable, not proof of zero cost |
| Unknown-usage attempts | 1 |
| Earlier614/615/618 ledgers | All byte-identical |
| Accepted candidate frames / boxes | 0 / 0 |
| New Jev training labels | 0 |
| Dataset / selected API models changed | No / No |
| Source/privacy review | C0 / I0 |
| Offline tests | 12 passed |

Positive admission would have required presence>=.85, confident counttwo, numeric Box confidences>=.8 and one-to-one IoU>=.7 against both frozen local LLM references. Nullable confidence would be rejected. Empty admission would require confident absence and countzero. All outputs would still be pending review candidates. These gates were not reached with a usable response.

Packet SHA256: d03b0f6ed912bb4737b7836621f664af08a8877aee653f804a14c897e36ada06
Runner SHA256: 8101bf3fdcb9ca3de7099a0950fb092d2b2b21b163af3af118365b97e6d301e4
Result SHA256: f547203cc22b2b23ec626af818f93bfe1f84bc2590e9c63688d74a045fd376b8
Ledger SHA256: fda3a650dda8fcca0b8707f1226abcba1f80826daf8f9826fe7ddea3a35bcc16

Do not reset or resend this pilot. Subsequent Codex-labelled TRAIN research data must keep its own provenance and must not be counted as Jev-assisted labels. No detector training or stable-trajectory improvement is established by this image diagnostic.
