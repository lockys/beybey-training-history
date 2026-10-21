# Optional local API publication579: ares-v1.3.115

The actual selected and scored115 weight is now an experimental option in the local API. Final live preservation checks completed with88choices and174registry files. All87prior choices and172prior files were preserved, together with the exact prior default and shared training state. There was no cloud synchronization or default promotion.

Weight SHA256:ce79428b8e5d783258c00570fdff6e7df9cf6809f5e15353859691d337b52092.

The weight comes from [training575](2026-10-21-native659-training-575.md):30epochs,4200TRAINforwards,280actual optimizer updates,selectedorder19/epoch20,consumedVAL81/1/4. Data659pairs/558TRAIN/54VAL/47TEST;14newpositiveTRAINimages/26source-onlyLLMboxes/zero new empties. The15inheritedhybridTRAINrows/30boxes remain human-confirmed false.

## Accuracy status

[Fixed regression577](2026-10-21-fixed-regression-577.md) did not establish improvement. Compared with114,fast45/2/7 remained unchanged;six77/4/9 became77/18/9;large320/26/4 became322/49/2;empty-frame FP increased1to3. Original qualification and per-session nonregression are false. An optional API choice is not an accuracy upgrade.

A separate retained-prediction check established the same seven correlated frame/object misses across110/113/114/115. Five have no proximity-only box at0.35;two already have nearby boxes with IoU below0.5. No lower-confidence conclusion or causal head attribution is established.

## Functional verification

Exactly one tiny synthetic clip with two generated black320x320frames at5fps was uploaded, and one job explicitly selected115. The effective modelSHA,YOLO/ByteTrack640/confidence0.35/NMSIoU0.5/fullROI settings matched. The job completed and annotation download returnedHTTP200. This checks functional model selection and download; it is not an accuracy benchmark or independent measurement of API neural-call counts.

Native prepare,publish,smoke-start,smoke-finish and final-preservation processes all exited0, with original handles and observation/terminal chains retained. No job resubmission,restart,resume or output reuse occurred.

One independent review covered13own sources,5named external sources and the complete curated577history. It foundC0/I1/M1. The Important import-order gap was repaired once:the full closed scoring evidence is hashed before importing external modules,and the reviewed own training policy is hash-checked and loaded by explicit file path. Four synthetic admission cases failed before repair and passed after repair. There was no rereview.

The Minor auxiliary-seal limitation is explicitly deferred:the source seal does not itself cover every auxiliary review receipt. Separate pinned root checks preserved the original review package,seven CPU receipts,reviewed history and root evidence before every operation. No general NULL-closure assurance is claimed.

Final preservation SHA256:8a8a79584eca9ebe6e6e1ef9dd4db889107c573d2986ef5bd72c62d74a5ef087.
Closed publication579 manifest:20400fe12dcc5cb9c843d95b9c8a0eff66fa27f68527b73cc20a80d6b87fef0f.

## Remaining goal

These are consumed LLM regression references and a synthetic functional test:source=llm,human_confirmed=false,new_independent_final_groups=0,stable_improvement_proven=false.

Final acceptance still requires at least3unused shooting sessions and at least300source-onlyLLM boxes frozen before predictions,Precision AND Recall>=90% at confidence0.35/one-to-oneIoU0.5,per-session results,emptyFP and exclusions. Human confirmation is not required.

Next work is a separately reviewed confidence-versus-geometry diagnostic. Existing source wiring shows that the30epochs updated only theP2branch;the head responsible for the persistent misses is not yet proved. Fixed benchmark thresholds and references remain unchanged.

Only this curated Markdown is intended for the designated training-history repository. No raw media,images,labels,weights,private code,paths,logs or credentials are included.
