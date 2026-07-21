# Hugging Face Spaces deploy notes

HF CLI/token was not available in the initial bootstrap environment. Each Gradio project is Space-ready:

- YAML frontmatter in `README.md`
- `app.py`
- `requirements.txt`
- `DISCLAIMER.md` + `input_guard.py`

## One-time setup

1. Create HF org or user (e.g. `Cross-Clinical`) matching GitHub brand.
2. `pip install huggingface_hub` and `huggingface-cli login`
3. For each Space repo:

```bash
huggingface-cli repo create health-pathway-explorer --type space --space_sdk gradio
huggingface-cli upload Cross-Clinical/health-pathway-explorer . --repo-type=space
```

Repeat for: `clinical-jargon-explainer`, `student-lit-helper`, `synthetic-case-quizzes`, `clinical-experience-resume`, `edu-medical-assistant`.

## Local smoke test

```bash
cd health-pathway-explorer && pip install -r requirements.txt && python app.py
```
