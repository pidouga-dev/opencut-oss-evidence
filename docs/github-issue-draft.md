# GitHub Issue Draft

Title:

```text
Add accessible description to onboarding dialog
```

Body:

```markdown
## Summary

When opening the editor for the first time, the onboarding dialog renders
without a DialogDescription / aria-describedby value. The browser console logs:

`Warning: Missing Description or aria-describedby={undefined} for {DialogContent}.`

## Why it matters

Adding a description improves accessibility for screen reader users and removes
the Radix/shadcn dialog warning during local development.

## Reproduction

1. Run the web app locally.
2. Open the Projects page.
3. Create a new project.
4. Open the editor.
5. Observe the onboarding dialog and console warning.

## Suggested fix

Add a screen-reader-only `DialogDescription` to the onboarding dialog, with the
description matching the current onboarding step.

I prepared a local patch:

`docs/onboarding-dialog-description.patch`

## Verification

The touched file passes:

`./node_modules/.bin/eslint apps/web/src/components/editor/onboarding.tsx`

The full repo lint currently fails on pre-existing issues in other files, so I
verified the changed file directly.
```

