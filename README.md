# delta-med

**Private medical AI that runs entirely on your own hardware.**

delta-med is installable software that lets a hospital, clinic, or laboratory run medical AI on-site. It reads scans, answers clinical questions, and transcribes notes without patient data ever leaving the building. A clinician reviews every output before it reaches a patient, and every inference is logged.

> **Status:** early development. Interfaces and supported models may change.

---

## Why delta-med

Healthcare providers currently face two poor options: send patient data to a foreign cloud AI service, or go without AI because building it in-house is too difficult. delta-med offers a third option: a self-contained, auditable system designed specifically for medicine and deployable on local infrastructure.

## Key features

- **Fully local.** Inference runs on hardware you own. No patient data is sent to external services.
- **Human in the loop.** AI output is held as a suggestion until a clinician explicitly approves it.
- **Validated models only.** A model cannot serve requests until it passes a validation run. Versions are pinned, with no silent updates.
- **Immutable audit trail.** Every inference is recorded, including which model version handled which encounter.
- **Grounded answers.** Responses draw on version-pinned clinical guidelines and cite their source.
- **Works with existing systems.** Supports FHIR, HL7, and DICOM so it can sit alongside current hospital software.
- **Offline-capable.** Designed for modest hardware and unreliable connectivity.

## Capabilities

| Area | Examples |
|---|---|
| Clinical reasoning | Guideline-grounded question answering, triage and referral drafts |
| Medical imaging | Chest X-ray and CT analysis, segmentation |
| Voice | Clinical dictation and note transcription |

Supported models are open-weight only, and each is routed to the inference engine suited to its type (llama.cpp, vLLM, SGLang, MONAI Deploy).

## Deployment tiers

Tiers are defined by clinical risk and setting. Each sets the validation required before a model can go live.

| Tier | Setting | Validation requirement |
|---|---|---|
| T0 | Single-provider clinic | Human review of every output |
| T1 | District hospital | Site-specific validation set |
| T2 | Referral hospital | Full validation and local ethics sign-off |
| T3 | Research or national center | Continuous monitoring and published results |

## Architecture overview

```
Clinical interface  →  Agents & workflows  →  Knowledge & retrieval
                              ↓
                    Model runtime (routing)
                              ↓
        Text engines · Imaging engines · Voice engines
                              ↓
        Data interoperability (FHIR / HL7 / DICOM)

   Safety, audit & governance and privacy controls span every layer
```

delta-med's own code handles routing, approval, logging, and integration. Inference itself is delegated to established open-source engines.

## Safety model

- Agents **propose; clinicians decide.** No autonomous action affects patient care without sign-off.
- Model outputs are decision support, not diagnoses. All supported models require validation before clinical use.
- Uncertainty and reasoning are shown to the reviewing clinician, not just the final answer.

## Extending delta-med

Third parties can package their own models as extensions. Each extension declares its clinical-risk tier and the validation evidence required, and is only activated once that evidence passes.

## Getting started

Installation instructions will be added as the first release stabilizes.

## Regulatory note

delta-med is not a certified medical device. Any deployment involving patient data requires appropriate ethics approval and regulatory review for your jurisdiction. This document is not legal advice.

## License

To be confirmed.