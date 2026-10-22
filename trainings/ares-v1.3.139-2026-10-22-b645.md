# Ares 1.3.139: matched hue training experiment

Date: 2026-10-22

Training and the independent post-terminal CPU audit completed successfully. This is the first new optimizer run in the 139–148 publication window. Version 137 is an existing matched comparator, not another newly completed run in that window. The historical completed-optimizer count is 138; interrupted run 134 remains excluded.

## Treatment

- Initializer: Ares 1.3.33.
- Seed: 46.
- Existing blur dataset: 558 training, 54 validation, 47 test frames.
- Compared with 137, the training hue gain changes from 0.015 to 0.5. Saturation 0.7, value 0.4, architecture, sampler, optimizer, learning rate and remaining settings stay matched.
- The observed training transform confirms hue 0.5. Validation augmentation is disabled.
- No new footage, independent final session or Jev annotation was added in this experiment. Labels remain LLM-derived and are not human-confirmed.

## Completed execution

- 30 epochs; 4,200 actual TRAIN forwards; 280 actual optimizer updates.
- 30 checkpoint files rehashed by the CPU auditor.
- 6,068 registered root-entry events; these exclude direct constructor forwards.
- The original worker and original CPU audit both returned exit 0.
- CPU audit used zero neural calls. Final source validation passed and retained the module-source inventory.

## Validation checkpoint selection

Selected epoch: 5 (zero-based checkpoint order 4).

| Fixed validation evidence | Result |
|---|---:|
| Frames / reference objects | 54 / 85 |
| TP / FP / FN | 82 / 1 / 3 |
| Precision | 82/83 = 98.795% |
| Recall | 82/85 = 96.471% |

Selection used the existing fixed validation rule, including minimum precision 98%. These are validation-set measurements, not human-confirmed general accuracy or proof of improved fast trajectories.

## Publication and next comparison

The fixed six-case, large-session, empty-frame and trajectory comparison of 137 versus 139 is being prepared separately. No improved fast-trajectory result is claimed here. The previous ten-run [128–138 evaluation](../evaluations/ares-128-138-2026-10-22-b643.md) remains a separate research record.

No weights were published to the API, no default was changed, and no new Greek-mythology name was assigned. This single matched comparison does not replace selecting five qualified models after ten new training runs or the latest-ten selectable-version limit.

## Byte identities

- Selected weight SHA-256: e182e1cc1b9835f91fb889698661241fbbf7c0c88cda4f5c9fb3e422637c39ec
- Training plan SHA-256: 6d1822f5b1e3ff7499ca6ae5b2ae50868da11ca605c9ed87179921cc5502078b
- Completion SHA-256: 661e88aefa7f40ac912f2639f1fa01584ab1cf18ff60d850e0c8d2b018412943
- CPU root validation SHA-256: bb95961b297e5675a406b67b5506f575542142c6689d5518586781af3aef289b
