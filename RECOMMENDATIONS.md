# Recommended next improvements for the Cross Clinical OSS suite

## Summary

This repo review suggests that the suite is already strong in mission, safety, and governance. The highest-value next step is to tighten the shared foundation and add automated quality checks so the portfolio remains maintainable as more student-facing tools are added.

## Priority recommendations

### 1) Standardize shared Python app scaffolding

Most Gradio apps follow a similar pattern: `app.py` entrypoint, copied `input_guard.py` rails, and corpus or glossary lookup. `edu-medical-assistant` does token-overlap retrieval; the others are mostly keyword or field lookup. That overlap is a good candidate for a shared template package or internal library. `oss-rails` is already the copy-source for guards, not a runtime dependency.

Recommended actions:
- create a lightweight shared library for common Gradio scaffolding
- centralize the input guard and disclaimer handling
- standardize corpus loading and retrieval helpers
- keep each app domain-specific and thin

Impact:
- lower maintenance cost across the suite
- easier onboarding for contributors
- fewer copy-paste mistakes across apps

### 2) Add automated tests to every educational app

`shadowing-hours-schema` already has `npm test` plus fixture validation. Gradio apps have syntax/JSON CI notes in [CI_CD.md](./CI_CD.md), but no unit tests for `guard_input` or app behavior. That makes regressions more likely in safety filtering, retrieval quality, and response formatting.

Recommended actions:
- unit test `guard_input` behavior on PHI and diagnosis cases
- verify retrieval ranking in apps that score corpus hits (currently `edu-medical-assistant`)
- smoke-test app startup
- validate corpus JSON files at import time
- add a small set of end-to-end checks for key study flows

Impact:
- higher confidence in release quality
- easier iteration on educational features
- fewer surprises in production demos

### 3) Centralize the safety policy and documentation

The repo already does a good job on disclaimers and refusal patterns. The next step is to treat those safety rules as a single shared contract across the suite.

Recommended actions:
- keep one canonical safety policy in the shared rails repo
- ensure all apps consume the same guard module
- document the do / do-not policy in one place
- review wording for clear educational-only boundaries

Impact:
- consistent product behavior
- easier auditability
- clearer external trust signals

### 4) Improve release and version tracking

The suite already indicates v0.1.0 in docs, but only `shadowing-hours-schema` ships a changelog. Stronger versioning discipline would help as the portfolio matures.

Recommended actions:
- adopt a release checklist for each repo
- publish changelogs for each toolkit
- keep Dependabot range bumps, and pin only when a Space needs a known-good install
- document compatibility expectations before release

Impact:
- cleaner handoff between prototype and product
- easier user understanding of stability
- more predictable maintenance

### 5) Create a root-level contributor workflow

The org has strong legal and operational docs, but a clearer contributor path would help scale the suite.

Recommended actions:
- add a single contribution guide for all repos
- define PR templates and issue templates
- document local setup and test commands
- add a recommended CI checklist for each app type

Impact:
- lower friction for new contributors
- more consistent repo hygiene
- easier multi-repo maintenance

## Why this matters

The current suite is already a compelling educational and career-technical portfolio. The best next step is not a broad rewrite; it is strengthening the common foundation so the projects are easier to maintain, test, and improve together.
