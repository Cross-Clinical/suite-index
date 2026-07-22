# CI / CD for Cross Clinical OSS

## What runs where

| Repo | CI | CD |
|---|---|---|
| `shadowing-hours-schema` | `npm ci` + `npm test` + validate fixtures | (optional) npm publish on release — add `NPM_TOKEN` later |
| `promednet` (private) | Node tests; validates against public schema | — |
| Gradio Spaces (6) | Python syntax, JSON validate, `pip install`, educational rails check | Optional HF sync on push if `HF_TOKEN` secret set |
| `observer-orientation-kits` | Kit file presence + PHI-pattern grep | — |
| `suite-index` | Suite repo link check via GitHub API | — |
| `oss-rails` | Hosts reusable Python CI workflow | — |

## Enable Hugging Face CD

In each Space repo (Settings → Secrets and variables → Actions):

1. Secret: `HF_TOKEN` (HF write token)
2. Variable (optional): `HF_USER` (default `Cross-Clinical`)
3. Variable (optional): `HF_SPACE` (defaults to repo name)

Then `sync-hf.yml` uploads on `main` pushes that touch app files, or via **Actions → Sync to Hugging Face → Run workflow**.

## Dependabot

Weekly pip/npm + monthly Actions updates on applicable repos.

## Auth note

Pushing workflow files requires a GitHub credential with the `workflow` scope:

```bash
gh auth refresh -h github.com -s workflow,repo,read:org,gist
```
