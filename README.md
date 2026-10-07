# delta-med

**Private medical AI that runs entirely on your own hardware.**

delta-med is installable software that lets a hospital, clinic, or laboratory run medical AI on-site. It reads scans, answers clinical questions, and transcribes notes without patient data ever leaving the building. A clinician reviews every output before it reaches a patient, and every inference is logged.


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

