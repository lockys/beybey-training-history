# Batch 581: copied-backend identity guard stopped the first warmup

Status: closed failed diagnostic; no completed prediction or new accuracy result.

## Purpose

The unchanged plan compared existing ares-v1.3.114 and ares-v1.3.115 on two
previously consumed fast-motion frames. The planned budget was 2 selected
model loads, 8 predictions and 10 observed DetectionModel root forwards,
including 2 GPU warmups. Confidence 0.35, diagnostic confidence 0.01,
IoU 0.5, full frame and image size 640 were unchanged.

## Actual result

The single native entry successfully loaded ares-v1.3.114 and began the first
prediction attempt. The global prehook rejected an unregistered DetectionModel
object at the first GPU warmup, before that root's forward body ran.
The entry exited with code 1. No prediction completed and no raw diagnostic
summary or accuracy result was produced.

The failed ledger records 1 completed selected model load, 1 incomplete
prediction attempt and 0 admitted root forwards. It records 0 optimizer
updates, 0 training epochs and 0 network attempts. These are the instrumented
entry counters, not a universal claim about all imported native libraries.

The native handle was observed terminal and retired. Shared training state
and the existing one-NUL lock content were preserved. The failed directory
is retained; it was not resumed, restarted or reused.

## Confirmed cause and next step

Static inspection of the installed BasePredictor.setup_model shows that it
deep-copies the selected model before backend setup. The diagnostic had
registered the original model object's identity. The backend therefore used
a distinct copied object, which the strict prehook correctly rejected.

The next isolated package must call the standard setup unchanged, then
verify and register its actual backend model before warmup. It must preserve
the global unknown-root rejection, exact execution budgets and four frozen
confidence-0.35 controls. This is an instrumentation lifecycle correction;
it does not establish which detection head caused any missed object.

## CPU and review evidence

PNG decoding was isolated using the same OpenCV and NumPy operation as the
frozen legacy reader. Both original frame arrays matched every pixel and the
invalid-image error matched. CPU geometry, snapshot, lock and budget checks
also passed. They are not neural prediction or accuracy evidence.

One independent whole-package review found 0 Critical, 0 Important and 1 Minor.
The minor issue concerned provenance wording only and was explicitly deferred:
the inherited 630-entry executable map contains the original 575 entries plus
55 legacy support files. No source repair or rereview followed that review.

This diagnostic adds 0 independent final sessions and proves no stable gain.
The original unused-session, frozen LLM reference, Precision AND Recall,
per-session, empty-frame and exclusion acceptance requirements remain unchanged.

Closed 581 evidence manifest SHA256:
e0caa02933c4dd2e31ce481effb651752f3d6cbbdc1d898ecf953d3966bf1be7
