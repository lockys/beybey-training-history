# Jev raw image diagnostics 618 - 2026-10-22

Three real jev-1.14.0 image requests completed with HTTP200 and retained typed judgments before unchanged candidate gating. They used the same3frozen public TRAIN crops, original questions and thresholds as615; only raw diagnostic retention was added. No dataset, reference label or default/catalog changed.

| Crop | LLM reference objects | Presence | Count choice/confidence | Box confidence | Raw Box/LLM reference IoU |
| --- | ---: | ---: | --- | ---: | ---: |
| Small blurred top near rail |1|0.32|none/0.33|0.11|0.398154 |
| Empty arena |0|0.42|one/0.28|0.19|N/A |
| Large blurred foreground top |1|0.68|one/0.77|0.25|0.770667 |

The large top's raw box agrees spatially with its LLM reference at IoU0.77, but both presence and Box confidence are below the frozen0.85/0.8thresholds. The small rail top is also a count/presence/localization failure in this example. The empty crop's presence0.42 exceeds the small positive's0.32, so a single presence threshold cannot separate both positives from this negative. Merely lowering the candidate gate is not supported by these observations. These3correlated crops are diagnostic examples from one source, not a calibration set, human-confirmed accuracy estimate, final trajectory evaluation or training-gain proof. Original source-only LLM references were never sent to Jev.

All3candidates remain no_supported_candidate; zero labels entered training. Raw diagnostics explicitly remain diagnostic_only, human_confirmed=false,training_eligible=false,candidate_admission_confirmed=false. The Box is never treated as an automatic empty/positive label. A local comparison plot shows raw orange boxes and frozen green LLM-reference boxes; no media is included in this repository.

Actual usage:2190input/246output tokens, zero unknown usage. Per-image latency0.500/0.282/0.297seconds; not a production benchmark. Prior614/615image attempts4 plus these3 reach the diagnostic cap7. Old ledgers are unchanged. No automatic retries or access workaround occurred. The previously verified new user credential was supplied by hidden input and remained process-only.

Source review of618and helper616 found0Critical/0Important/0Minor. Offline dry-run3receipts,0calls. Original live process session25955,launch3790c0,terminal0212c9,exit0. Independent readback confirms3success rows and exact usage; all image/source/packet hashes, earlier ledgers and raw-judgment/receipt identities match. This is the first real use of the616observer; its original8synthetic/fake tests are separate evidence.

Evidence SHA256:

- Packet:d5cd5e3b0dd5d75048eb1fc7acc04e3ccd7edbb0e76a535e17650aca4aabbc40
- Source review:d2c5a6b567377dae3953f859a7a392c4f977b35d889032689cfecd3f8604c84f
- Result:36f0fefe362d7ba1f3caee74655befd3328e3753a25786045f168cf4f8bc67da
- Completed journal:4c8154b8605f5bb59f234f96a51cedfbd6e37c82d26ead320b1963266bf20d5f
- Raw judgments1:e9e85e95b71afbcff14a0b0289094b6953d814668318a1ded7bbea457bdd3495
- Raw judgments2:7561297a59b26f971ac99f61ce21cec76eaf45fb506f311ab3beb4142279505f
- Raw judgments3:7372d672f655c8948ba00a17a802532cfb1429d414d28f8213d988abcc6b1190
- Locally rendered comparison plot:8183713bc9298c2b36443e71614713255e055245b73391f955abf16daaed4356

No additional full optimizer run is claimed by this API experiment. Completed full-run count remains131, with132running. Jev/Laya training labels added0; new independent final groups0; stable trajectory improvement unproven. Next annotation work should test blur-aware object wording and context on a separately frozen TRAIN diagnostic set, without tuning reserved final references or automatically lowering thresholds.
