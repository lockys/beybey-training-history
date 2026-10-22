# Ares 1.3.141: native blur training completed; trajectory comparison pending

**Thirty full epochs completed and the original native training process exited successfully.** A separate CPU audit also exited successfully. This is a research checkpoint; no API/default change or stable trajectory improvement is established.

## Training and data

The dataset contains 662 frames: 561 TRAIN, 54 VAL and 47 TEST. It retains the frozen 659-frame baseline and appends three native TRAIN frames from existing TRAIN-only video sessions: four cross-reviewed Codex LLM boxes and one empty frame. These are not human-confirmed or Jev-generated labels. They add no new independent final-evaluation session.

An exact dataset clone was staged inside batch653 so Ultralytics label caches remain within the existing worker write boundary. Original dataset bytes and the outside-write guard were preserved.

The recipe uses the Ares 1.3.33 initializer, seed46, standard three-scale architecture, batch4, 640px, 30 epochs, AdamW learning rate0.00005 and HSV0.015/0.7/0.4. Every TRAIN frame is traversed each epoch. The larger dataset requires 4,230 TRAIN forwards versus comparator137's 4,200, so forward budgets are not identical.

| Observed result | Value |
| --- | ---: |
| Completed epochs | 30 |
| TRAIN forwards | 4,230 |
| Optimizer updates | 282 |
| Changed parameter tensors | 251 |
| Selected checkpoint | epoch4 / zero-based order3 |
| VAL reference boxes | 85 across54 frames |
| Selected VAL TP / FP / FN | 82 / 1 / 3 |
| Network / API / protected-read / outside-write events in141 | 0 / 0 / 0 / 0 |

Selection used VAL only. VAL labels are LLM references, not human ground truth. The selected TP/FP/FN match comparator137 and do not prove improved detection or trajectories. TEST was not used to select weights.

The original141 native training handle12671 terminated at chunk006b7d with exit0. Its CPU audit handle33401 terminated at chunk15e539 with exit0. The audit rehashed30 checkpoints,1,362 bound inputs and45,137 executable files, and checked the epoch traversal, optimizer journal, native identity and source closure without neural calls.

Cumulative observed constructor/fresh-model/load counters are32/2/67, including failed140's1/1/1 costs. Other observed counters are6,098 registered roots and1,620 predictions. Run140 stopped before any forward or optimizer update and is excluded from completed training counts, as is134. The total full optimizer completion count after141 is139. The new ten-completion window currently contains completed139 and141; failed140 does not fill a slot.

## Availability and remaining evidence

The selected research weights have SHA256 `6bb4941f7e5bc1a6473a770b0d9c232d31cf060f426104557f8df98abaffffc2`. They are not published to the API. No five-winner cohort or new Greek model name is claimed.

The planned fixed137-versus141 comparison must still measure fast/blurred trajectory coverage, gaps, association errors, each session's TP/FP/FN and empty-stadium false positives. Comparison652 remains unassembled and has not executed neural inference. The configured workspace still names the missing spintrail directory, and the tool refused a required fresh read of the141 completion record. These access issues await host-side correction; no alternate read or skipped authentication has been used.

Jev pilot648 previously produced no usable typed response and accepted zero labels; none of this delta is attributed to Jev. No retry of that closed pilot occurred.

## Evidence digests

- Dataset manifest: `701a28083309f083c82885adc10b7a4f5009b93835a77483053c323f3a331ecd`
- Training planV2: `0c6df141115bfbccf2b3c6966f321c2f5dc0f65bffceef696667c09db01511b2`
- Source review: `4714bc5d601357a92ff42229a4ede9dbd3a9fc531bf7c3eab49d334e236e3548`
- Source release: `56f9ada59f848c865806687b81e2a589b7470244d9482cb012ca12ef243c4728`
- Activation: `a8346445ebecdab5c1a33449515e049edfcc3b206acd6a7c1bc6f6d829e57178`
- Native launch: `7c1cedc9563804fecae4e3a34e728517da9fb6ce2c74dde861ec7e98e0b0aac8`
- Completion: `0bbf1e4f9025fe02e876fd0eed3e4ffb2c61fbd3072592273708a8fbe7b0d855`
- Native terminal: `b781055b7c4add771efbea99adf36179d7252402eefba8b112709e4ba27c4d37`
- CPU root validation: `de350818c11bd685ee70f601a17cb24e067803e60f0f58ee0471cf6510353e84`
- CPU audit native terminal receipt: `fd37b7ebd15cade579cf85e0e8c8845458a5fd67af76156e213e54bff7589d31`
