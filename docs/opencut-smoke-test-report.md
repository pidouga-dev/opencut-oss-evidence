# OpenCut Smoke Test Report

Date: 2026-06-05 JST

## Scope

This report records a local evaluation of OpenCut Classic in a clean workspace.
The goal was to create public-safe OSS evidence without exposing personal
information, API keys, or private data.

## Source

- Repository cloned: `https://github.com/opencut-app/opencut-classic.git`
- Local path: `/Users/saitouhikaru/Documents/New project 6/opencut-classic`
- App URL during test: `http://localhost:3000`

## Environment

- macOS local workspace
- Bun available at `/Users/saitouhikaru/.bun/bin/bun`
- Docker was not available in the shell environment
- ffmpeg available at `/opt/homebrew/bin/ffmpeg`

## Steps completed

1. Cloned `opencut-app/opencut-classic`.
2. Created `apps/web/.env.local` from `.env.example`.
3. Confirmed `.env.local` is ignored by Git.
4. Installed dependencies with `bun install`.
5. Started the web app with `bun run dev:web`.
6. Opened `http://localhost:3000`.
7. Created one OpenCut project from the Projects page.
8. Opened the editor for the generated project.
9. Opened the Text panel and attempted text placement.
10. Captured screenshots and console warnings.
11. Created three synthetic media assets for future import testing.
12. Created a small accessibility patch for the onboarding dialog warning.

## Evidence screenshots

- `screenshots/01-project-created.png`
- `screenshots/02-editor-opened.png`
- `screenshots/03-text-panel.png`
- `screenshots/04-text-added-attempt.png`
- `screenshots/05-text-dragged.png`

## Generated media assets

- `media/opencut-smoke-test-01.mp4`
- `media/opencut-import-asset-02.mp4`
- `media/opencut-timeline-asset-03.mp4`

These are synthetic ffmpeg outputs using color bars, test patterns, and sine
audio. They do not contain third-party media.

## Findings

### App startup

The app started successfully and rendered the OpenCut landing page and project
workspace.

### Project creation

Project creation from the empty Projects page succeeded. A project named
`New project` was created and opened in the editor.

### Editor access

The editor rendered successfully with Media, Sounds, Text, Stickers, Effects,
Transitions, Captions, Adjustment, and Settings panels.

### Text panel observation

The Text panel displayed a `Default text` card. Clicking the card did not add an
element during this automated smoke test. A drag attempt was also attempted, but
no timeline element was added in the captured state. This may require manual
browser interaction, a supported file/drop API, or a UX/accessibility follow-up.

### Console warning

The browser console showed the following warning after the onboarding dialog:

```text
Warning: Missing `Description` or `aria-describedby={undefined}` for {DialogContent}.
```

The local patch in `docs/onboarding-dialog-description.patch` adds a hidden
`DialogDescription` for each onboarding step.

## Verification

- `bun run lint:web` was executed and failed due to existing repository-wide
  lint issues outside the touched file.
- `./node_modules/.bin/eslint apps/web/src/components/editor/onboarding.tsx`
  passed for the touched file, with only the repository's Next pages-directory
  warning printed.

## Public release checklist

- No `.env.local` files included.
- No API keys included.
- No account identifiers included.
- No personal name or email included.
- Generated media only.

