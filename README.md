# OpenCut OSS Evidence Pack

This repository contains public-safe evidence from a local OpenCut evaluation
session. It is designed as a small, honest artifact pack for OSS application,
issue triage, and contribution tracking.

## What is included

- `screenshots/`: local OpenCut screenshots showing project creation and editor access.
- `media/`: generated test media for OpenCut import/timeline smoke testing.
- `docs/opencut-smoke-test-report.md`: environment, steps, findings, and privacy notes.
- `docs/github-issue-draft.md`: issue draft for an onboarding dialog accessibility warning.
- `docs/onboarding-dialog-description.patch`: local patch that adds a screen-reader-only dialog description.
- `docs/openai-codex-for-oss-application-draft.md`: draft application text with placeholders only.

## Public contribution links

- Evidence repository: `https://github.com/pidouga-dev/opencut-oss-evidence`
- OpenCut fork with patch branch: `https://github.com/pidouga-dev/OpenCut/tree/codex/command-dialog-description`
- Upstream issue: `https://github.com/OpenCut-app/OpenCut/issues/814`

The upstream OpenCut repository currently limits pull request creation to
collaborators, so the patch is linked from the public issue instead of a PR.

## Privacy and safety

No personal data, API keys, auth tokens, private repository URLs, customer data,
or account identifiers are included. The generated media uses only ffmpeg
synthetic sources.

## Important eligibility note

The OpenAI Codex for Open Source program is intended for open-source
maintainers and widely used public projects. This pack should not be used to
claim maintainer status for a project unless that is true. Use it as supporting
evidence for real OSS usage, contribution, or a good-faith nomination.
