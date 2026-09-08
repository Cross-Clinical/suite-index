# Contributing to Cross Clinical OSS

Thank you for helping improve our educational tools. Every public repo in [Cross Clinical](https://github.com/Cross-Clinical) shares the same contributor expectations.

## Before you start

- Read [DISCLAIMER.md](./DISCLAIMER.md). These projects are **educational only** — not medical advice, not for diagnosis, and never for PHI.
- Follow the [Code of Conduct](./CODE_OF_CONDUCT.md).
- Sign commits with DCO: `git commit -s` ([DCO.md](./DCO.md)).

## Local setup (Gradio apps)

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
python app.py
```

## Local setup (schema package)

```bash
npm ci
npm test
npm run validate
```

## What to change where

| Change | Repo |
|--------|------|
| Shared disclaimer / input guard | `oss-rails`, then copy into Gradio apps |
| Shadowing hour record schema | `shadowing-hours-schema` |
| Portfolio index / CI docs | `suite-index` |
| App-specific corpus or UI | That app's repo |

When `shadowing-hours-schema` changes, re-copy the schema into `clinical-experience-resume/schema/` before release.

## Pull requests

1. Keep PRs focused — one concern per PR when possible.
2. Run local tests before opening:
   - Gradio apps: `python -m unittest discover -s tests -p 'test_*.py' -v`
   - Schema: `npm test`
3. Do not weaken PHI or diagnosis guards without an explicit security review.
4. Link related suite-index docs when changing cross-repo behavior.

## Security

Report vulnerabilities privately per [SECURITY.md](./SECURITY.md).

## Questions

https://crossclinical.com
