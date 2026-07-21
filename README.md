# Cross Clinical — Open Source Suite

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Cross Clinical](https://img.shields.io/badge/Cross%20Clinical-OSS-0B3D2E)](https://crossclinical.com)
[![ProMedNet](https://img.shields.io/badge/ProMedNet-waitlist-1F6F5B)](https://crossclinical.com)

Educational and career tools for health professions students — **not medical advice**, **not for diagnosis**, **no PHI**.

Closed products ([ProMedNet](https://crossclinical.com) networking + hosted shadowing ops) stay private. This index lists public OSS only.

## Portfolio

| ID | Repository | Status | HF Space? |
|----|------------|--------|-----------|
| S1 | [shadowing-hours-schema](https://github.com/Cross-Clinical/shadowing-hours-schema) | v0.1.0 | No (npm/schema package) |
| S2 | [health-pathway-explorer](https://github.com/Cross-Clinical/health-pathway-explorer) | v0.1.0 | Yes (`app.py`) |
| S3 | [clinical-jargon-explainer](https://github.com/Cross-Clinical/clinical-jargon-explainer) | v0.1.0 | Yes |
| S4 | [student-lit-helper](https://github.com/Cross-Clinical/student-lit-helper) | v0.1.0 | Yes |
| S5 | [observer-orientation-kits](https://github.com/Cross-Clinical/observer-orientation-kits) | v0.1.0 | Optional static |
| S6 | [synthetic-case-quizzes](https://github.com/Cross-Clinical/synthetic-case-quizzes) | v0.1.0 | Yes |
| S7 | [clinical-experience-resume](https://github.com/Cross-Clinical/clinical-experience-resume) | v0.1.0 | Yes |
| S8 | [edu-medical-assistant](https://github.com/Cross-Clinical/edu-medical-assistant) | v0.1.0 | Yes |
| — | [oss-rails](https://github.com/Cross-Clinical/oss-rails) | shared | Disclaimer + input_guard template |

## Hugging Face Spaces

Each Gradio app is Space-ready (`README.md` YAML + `app.py` + `requirements.txt`).

Deploy (requires HF account linked to org):

```bash
# Example
huggingface-cli upload Cross-Clinical/health-pathway-explorer ./oss/health-pathway-explorer --repo-type=space
```

See [HF_DEPLOY.md](./HF_DEPLOY.md) in this monorepo workspace or each repo README.

## Shared rails

- MIT license
- [DISCLAIMER](https://github.com/Cross-Clinical/shadowing-hours-schema/blob/main/DISCLAIMER.md) on every project
- Input guards against PHI-like and diagnosis intents in Spaces
- DCO for contributions

## Kill criteria (day 45 / day 90)

Archive a project if 2+ apply: low organic use, no ProMedNet inbound, unsustainable maintenance, or users treat it as a doctor after prompt hardening.

Prefer preserving **S1, S2, S5** (closest to company wedge).

## Not in this suite

- Full shadowing scheduler / hospital multi-tenant ops (closed)
- ProMedNet social graph (closed)
- Imaging diagnosis demos
- Deep bioinformatics toolkits

## Contact

https://crossclinical.com
