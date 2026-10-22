# Training preparation606 and Jev offline integration607

Date: 2026-10-22 Asia/Taipei
Status: offline preparation only; no new training or live Jev inference.

## Training accounting

Actual completed optimizer-backed training runs remain127. The latest completed
block118-127 produced zero eligible selections under the frozen detection,
each-empty-frame and trajectory gates. No API model, default, weight digest or
Greek model name changed in this preparation stage. API catalog target/retention
work remains unresolved; this record is not proof of a live ten-choice cap.

## Balanced motion-blur comparison data

Prepared two fresh local datasets, each659 pairs:558TRAIN,54VAL,47TEST.
Control images retain original bytes. The blur arm replaces exactly89 positive
and23 empty TRAIN images with deterministic mild linear motion blur. This is
20% of444 positive frames and20% of114 empty frames, with constant pair counts.
Each arm preserves all659 labels and all101 VAL/TEST images byte-for-byte.
Original1318 image/label digests and manifest were verified before/after staging.
All2642 output files across both arms are bound by the local audit.
Original source bytes were unchanged. No new source frames, label boxes or
independent final shooting groups were added. Inherited LLM labels remain
pending and human_confirmed=false. This does not establish physical accuracy.
Data-only audit SHA256:
d89b3bd4e4d9bf15c24365949594f6fb59c3f4fc90039ded843f83d86751d827
Seven synthetic-fixture data tests passed. Neural execution is not admitted yet.

## Jev assistance prototype

Official image and Box capabilities were checked. Images/Box are experimental;
Box needs Jev1.14. Proposed use: difficult-frame triage and independently checked
candidate annotation, followed by controlled YOLO training. No measured Jev
accuracy, latency, cost or trajectory improvement is claimed.

Added disabled persistent SQLite attempt accounting around the existing offline
candidate/Pilot prototypes. Reservations precede supplied transport calls;
packet, request, image, complete Pilot policy and budgets are bound across
restarts. Unknown, failed, duplicate, concurrent and exhausted attempts stop.
Known token limits are retrospective and are not a vendor monetary cap.

One fresh read-only whole-packet review found0Critical/1Important. The Important
issue was that transport success preceded full candidate/expiry validation.
Two behavioral tests reproduced incorrect second sends after restarting.
A single fix pass now retains blocking received state with known usage, and
finalizes success only after the complete pinned Pilot accepts the candidate.
Parsing/expiry failures remain durably stopped. Fourteen ledger/integration tests
passed, including an actual abruptly exiting child process and a synthetic PNG
through the existing Pilot. Existing candidate11 and transport31 tests also
passed. These56 Jev-related tests used synthetic fixtures and fake transports.
No second review was requested. No real provider call or configured-key read,
frame upload, new training label or production integration occurred.

Before a real pilot: verified source/export and crop provenance, frozen
independent source-only references, calibration, actual budget and complete live
packet review. Candidate output remains review_only, human_confirmed=false and
training_eligible=false; an absent candidate is not an automatic empty label.

## Evidence limits

No stable independent trajectory gain, three new final sessions,300 new frozen
source-only reference boxes, physical-device validation, new deployed model or
full-project green test suite is established by this work. All existing fixed
nonregression, independent final acceptance and model-retention gates remain.
Only this aggregate history is published; no media, labels, private source code,
weights, credential, raw provider response or logs accompany it.
