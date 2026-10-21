# Paired campaign596: completed training run125

Published2026-10-22 Asia/Taipei. Actual optimizer-backed progress8/10 completed
runs(118..125). Stable fast/blur trajectory improvement remains unproven.

## Execution and audit

ares-v1.3.125 used seed45/freeze11: attention10 and backbone0..10/DFL frozen,
neck/heads trainable. Runtime measured169trainable parameter tensors and
241frozen state entries. Same selected117 initializer,659pairs
(558TRAIN/54VAL/47TEST),847TRAINboxes/114TRAINnegatives,640/batch4,30epochs,
fixed sampling/loss/AdamW/nominalLR1e-6 with actual-step multiplier100.
Historical15hybridTRAINrows/30boxes remain declared; no new training data.

Original native21915 terminal67e20a exit0. Owned launcher46904 and worker65296
were distinct.30epochs,4200actual TRAINforwards,280optimizer updates,
6075observed DetectionModel roots. Constructor-directforward calls may bypass
those hooks; not a universal physicalNN-operation count. No retry,resume,
restart or concurrent neural job.

Stdlib audit a2adf9/session84091 ->8b4f15 exit0 verified2657training inputs,
630executable origins,13frozen prospective sources,30checkpoint hashes,
assignment,sampling,per-head/per-feature gradients,restoredLR and VAL selection.
No model deserialization or neural calls in that checker. Frozen tensor equality
relies on reviewed runtime live/saved checks,not independent tensor inspection.

## VAL-selected checkpoint

13/30 checkpoints met fixed VAL precision>=.98. Selected order2 is the third
epoch. Fixed conf.35/NMS.5/one-to-oneIoU.5 on54frames85LLMboxes:
TP81/FP1/FN4,precision98.78%,recall95.29%.

| VAL session | TP | FP | FN |
| --- | ---: | ---: | ---: |
| youtube-mI4qN8iV0h0 | 23 | 0 | 0 |
| youtube-gTx9as_nf10 | 12 | 0 | 0 |
| youtube-X8Ab_zjm5H0 | 19 | 0 | 1 |
| shark-event | 3 | 1 | 1 |
| youtube-pmEIYBfQYzQ | 24 | 0 | 2 |

Native24677c authenticated initializer117 selection81/1/4:allfive sessions
exactly equal. Versus same-seed attention-trainable124(80/1/5),pmEIY gained1TP/
lost1FN; otherfour sessions and allFP unchanged. No significant or stable gain
is established. This VAL result is not the post-ten fast/six/large/trajectory
eligibility decision,and no new unplanned gate or per-model tuning is added.

Stock CSVrow3:mAP50 .97986,mAP50-95 .6767,P .98765,R .94048 at its
confidence-sweep operating point. Keep it distinct from fixed.35 measurements
and physical/independent final accuracy. Evaluation references remain
source=llm,human_confirmed=false,review_status=pending.

## Identities and preparation

Selected weightSHA256:
d956112cf0be3976a73128c3f7a6d4b16b00335ffb6ba052dafc1d8b92724b0a
CompletionSHA256:
5f6b0f405191f1f609d71e031afa4c131d505c60021c0b23a1a8f8861f23c8cd
RootvalidationSHA256:
7cec875b3477fe0c0b2a95fbdd344cddbc49f72681b3a1db18c0596e5946234d

No new125fast/six/324/trajectory scores yet. Aftertencompleted actualruns,
authenticate selectedweights/root/nativeproofs and use identical frozen
detector/tracker inputs. Apply original1.2.2per-case/session/each-emptyTP/FP
and33per-case measured/certain/identity/gap nonregression,then frozen596ranking.
Recommend at most5actuallyeligible candidates,fewer if fewer pass. Equality
allowed;no extra588web gate or per-model label/threshold/tracker adjustments.

CPU decoder check9738d8 executed unmodified source-pinned decoding function
bodies and found identical uint8/BGR pixels on all175large-cohort PNGs.
No product/Ultralytics package imports,model loads or NN calls; decoder
equivalence alone is not fullfrontend/inference quality evidence.

PreparedIO603 passed12local fixture tests after observed RED17behaviorfailures.
Checks include exact-byte input hashes,exclusive run/output creation,drift/
duplicateJSON rejection and bounded metadata journal chain/fsync failure stop.
These are localfixture results,not actualscoring admission or power-loss proof.
The caller-supplied hash map still needs external authentication. Complete
worker/backend/lease/networkdeny/actualtracker/rawauditor and wholepacket
review/admission remain necessary;601/602/603tests grant no liveNNapproval.

One bounded batch of four public new-source metadata searches admitted0videos.
Existing594/598duplicates were skipped without fetch/retry/alternate route.
No new media,frames,labels or independentfinal groups. This does not establish
that no suitable public source exists. Still0new independent finalgroups.

API/menu/sharedstate/default unchanged by this run;no deployment or Greek name.
Choice policy remains<=10total including unchangeddefault. Fullstable acceptance
still>=3unused sessions,>=300source-onlyLLMboxes frozen before prediction,
P and R>=90%,per-session/empty/exclusion evidence and actual consecutive
production low-confidence tracking. Jev remains offline/fake-transport only,
actualrequests0. Only aggregate text published: no media,weights,labels,
private source,credentials or full logs.
