# Batch580: diagnostic entry stopped before model loading

Status: closed failed entry; no new accuracy result and no stable-improvement claim.

## Purpose and planned budget

The diagnostic was planned to compare existing ares-v1.3.114 and
ares-v1.3.115 on two previously consumed fast-motion frames.
The unchanged plan allowed 2 model loads, 8 predictions and 10 observed
DetectionModel root forwards, including 2 GPU warmups.
Confidence 0.35 remained the fixed evaluation setting; 0.01 was diagnostic only.
IoU remained 0.5. No new labels, training, source exports or final test sessions
were planned.

## Actual native result

The single native entry exited with code 1 while importing the legacy image
reader. Its module also imports video/tracking dependencies, and the isolated
entry did not expose the beytrack package namespace.
The error was ModuleNotFoundError for beytrack.

The preserved failed ledger records 0 scheduled model loads, 0 predictions,
0 observed root forwards,0 optimizer updates and0 network attempts.
No completion or prediction result was produced. These ledger counters are
not a claim that all imported native libraries were independently instrumented.

The original native handle was observed terminal and retired. The failed
directory is preserved; no resume, restart or output reuse was performed.
Shared training state and the existing one-NUL lock content were preserved.

## Review and CPU evidence

One independent whole-package review reported 0 Critical, 2 Important, 0 Minor.
One root repair pass fixed the Windows locked-file second-handle read and
the independent checker accepting incomplete or corrupt summary fields.
No rereview was performed.

CPU regressions reproduced both defects before repair and passed afterward.
The checker accepted 3 complete synthetic summaries, rejected 18 corrupt
summaries and 7 malformed raw inputs. The lock fixture check did not touch
the real shared lock. This is CPU behavior evidence, not model accuracy.

## Next action and limits

Use a new isolated diagnostic package with verified PNG decoding behavior,
then perform the same bounded diagnostic after its source review.
Do not change references, matching thresholds or final acceptance criteria.
This failed entry adds 0 independent final sessions and proves no stable gain.

The separately verified optional local API 115 delivery is recorded in
runs/2026-10-21-optional-local-api-579.md. It is a functional delivery result,
not evidence that 115 improved fast-motion recall.

Closed 580 evidence manifest SHA256:
eb8255a5e156921f0a463296899294c0a2f906f07d7dd5eaee09fa8c91f67576
