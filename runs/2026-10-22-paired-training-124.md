# Paired campaign 596: completed training run 124

Published 2026-10-22 Asia/Taipei. Actual optimizer-backed progress7/10
completed runs (118..124). Full stable fast/blur trajectory goal remains unmet.

## Execution and audit

ares-v1.3.124 used seed45/freeze10: attention10 plus neck/heads trainable;
backbone0..9 and DFL frozen. Runtime measured190 trainable parameter tensors
and199 frozen state entries. Same selected117 initializer,659 pairs
(558 TRAIN/54 VAL/47 TEST),847 TRAIN boxes/114 TRAIN negatives,640/batch4,
30epochs,fixed sampling/loss/AdamW/nominalLR1e-6 and actual-step multiplier100.
Historical15hybrid TRAIN rows/30boxes remain declared in the frozen manifest;
no new source footage or labels were introduced.

Original native7139 terminalddcb02 exit0. Owned launcher69168 and worker55660
were distinct. 30epochs,4200actual TRAIN forwards,280optimizer updates,
6075observed DetectionModel call roots. Constructor-directforward calls may
bypass those hooks; this is not a universal count of physical neural operations.
No restart,resume,retry or concurrent neural job.

Stdlib root audit73f8c8/session56907 ->11812a exit0 verified2657training inputs,
630executable origins,13frozen prospective sources,30checkpoint hashes,
sampling,assignment,per-head/per-feature gradients and restored learning rates.
No model deserialization or neural calls in that checker. Exact frozen tensors
are supported by reviewed runtime live/saved checks, not independent checkpoint
tensor inspection by the stdlib auditor.

## VAL-selected checkpoint

10/30 checkpoints qualified under fixed VAL precision>=.98.
Selected order6 is the seventh epoch. Fixed conf.35/NMS.5/one-to-one IoU.5
on54frames85LLM boxes:TP80/FP1/FN5,precision98.77%,recall94.12%.

| VAL session | TP | FP | FN |
| --- | ---: | ---: | ---: |
| youtube-mI4qN8iV0h0 | 23 | 0 | 0 |
| youtube-gTx9as_nf10 | 12 | 0 | 0 |
| youtube-X8Ab_zjm5H0 | 19 | 0 | 1 |
| shark-event | 3 | 1 | 1 |
| youtube-pmEIYBfQYzQ | 23 | 0 | 3 |

Native22902d authenticated initializer117 selection81/1/4. pmEIY lost1TP
and gained1FN; other four sessions and all FP were unchanged. This is a VAL
regression observation, not a new eligibility gate or final six/large/trajectory
decision. The same-seed freeze11 control125 has not completed at this report.

Stock CSVrow7:mAP50 .9784,mAP50-95 .69241,P .98731,R .95294 at its
confidence-sweep operating point. Keep it distinct from the fixed.35 gate
and physical/independent final accuracy. Evaluation references remain
source=llm,human_confirmed=false,review_status=pending.

## Identities and evaluation preparation

Selected weight SHA256:
6dea618aaf7ed77307d2197d5e048225ebc3ca51ee7870b84a7619ea7b75b2d5
Completion SHA256:
f5a2220870875c3403fd01d796a702a4e413af6418a4275e0247a91d58ec2b16
Root validation SHA256:
b18390f52e9fcd2c0a6b6bec5b94523576194c88251de81aca777cd00abc0558

No new fast/six/324/trajectory scores for124 yet. After ten actual completed
runs,authenticate selectedweights and use the identical frozen detector/tracker
profile and original1.2.2per-case/session/each-empty TP/FP gates plus33per-case
measured/certain/identity/gap nonregression. Apply the frozen596 ranking and
recommend at most5trulyeligible candidates,fewer if fewer pass. Equality is
allowed; no per-model threshold/tracker/label tuning or extra588web gate.

Partial ledger602 preparation passed21synthetic CPU behavior tests, including
failed backend BudgetError stop-latching and eighth-constructor rejection.
A synthetic601producer/602ledger link consumed7fakefactory/236fakepredict
callbacks and243simulated root-entry events. Actual models,NN,new predictions,
source-media reads and training from these fixtures were0. Fake device/stride/
grad/tensor flags are not CUDA or inference evidence. The ledger observes only
registered root entries after construction; constructor-directforwards are
unobserved and entries can fail before completing. Its planned per-candidate
cap is7backend constructionattempts/236predictattempts/472observedrootentries.
It has no actual whole-worker review/admission,OSlease,authenticatedIO,
networkdeny,durablejournal or complete real tracker/auditor integration.

API/menu/sharedstate/default unchanged by this run; no deployment or Greek name.
API choice policy stays at most10total including unchanged default.
Still0new independent final groups. Stable acceptance requires>=3unused
sessions/>=300source-onlyLLM boxes frozen before prediction,P and R>=90%,
per-session/empty/exclusion evidence and actual consecutive production
low-confidence tracking. Jev remains offline/fake-transport only,actual calls0.

Only aggregate text is published; no media,weights,labels,private code,
credentials or full logs are uploaded.
