# tibanode

**Private medical AI that runs entirely on your own hardware.**

tibanode is open-source software that lets a hospital, clinic, or laboratory run medical AI on-site. Patient data never leaves the building. A clinician reviews every output before it is used, and every action is logged.

> Research software. Not a certified medical device. Not for clinical use unless validated and approved at your site.

## Why delta-med

Healthcare providers and AI labs usually face two poor options:

>send patient data to a foreign cloud AI service and, 
>Go without AI because building a safe system in-house is too hard. 

tibanode is a third option: a self-contained, auditable system built for medicine that runs on local infrastructure.

## Key features

- **Fully local.** Inference runs on hardware you own. No patient data is sent to external services or to the cloud.
- **Human in the loop.** AI output stays a suggestion until a clinician explicitly approves it.
- **Validated models only.** A model cannot serve requests until it passes validation. Versions are pinned, with no silent updates.
- **Tamper-evident audit trail.** Every action is recorded, including which model version handled which encounter, and the log can be verified offline.
- **Grounded answers.** Responses draw on version-pinned clinical guidelines and cite their source. When evidence is thin, the system says so.
- **Works with existing systems.** Supports FHIR, HL7, and DICOM so it can sit alongside current hospital software.
- **Offline-capable.** Built for modest hardware and unreliable connectivity.
- **Swahili and English.** Designed for clinicians who work in both languages.

## Capabilities

| Area | Examples |
|---|---|
| Clinical reasoning | Guideline-grounded question answering, referral and note drafts |
| Medical imaging | Chest X-ray and CT analysis, segmentation |
| Voice | Clinical dictation and note transcription |

## Contributing

Contributions are welcome. Please open an issue before starting a large change. Never commit real patient data.

## Security

Report vulnerabilities privately using GitHub's private vulnerability reporting. Never include patient data in a report.

## License

Apache-2.0
