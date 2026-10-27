# TRAIN task assignment and raw-logit gradient diagnostic

Protected Ares33, four persistent TRAIN misses only; same640square letterbox and existing curated body labels. Four CPU forwards/backwards through actual vendor loss and public TaskAlignedAssigner output; zero optimizer instances/updates. Cached teacher class scores reproduced, all model states unchanged, no network/API action. No VAL/TEST/development/full-acceptance inference, new labels, threshold changes or189training changes.

Each target receives10positive anchors. All40positive anchor class-loss logit gradients are negative: an isolated raw-logit gradient step would increase these logits. Thus these four examples do not lack positive assignments or upward logit supervision under this unaugmented setting.

Frames458/459/535: the previously frozen teacher-best aligned anchors are assigned positive with soft targets0.685328/0.596440/0.795535, class probabilities0.126794/0.149738/0.202150, gradients-0.024570/-0.022797/-0.065195. Frame522's frozen teacher-best IoU-aligned anchor1333 has probability0.001007 but is not assigned to that GT: soft target0 and gradient+0.000184. Its10other positive anchors all receive upward gradients, with maximum probability0.000863 and positive-set gradient sum-0.499162. Therefore the single frozen anchor is an incomplete proxy for learning at this target.

This is local TRAIN-gradient evidence, not validation accuracy, proof of feature insufficiency, optimizer-step behavior or future improvement. Shared parameter gradients, augmentation, batch target normalization and optimizer history can differ. Original189experiment, selected checkpoint protocol, acceptance gates and API remain unchanged.
