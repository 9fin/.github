<!--
Title: start with a conventional commit prefix (feat:, fix:, chore: ...).
See https://www.conventionalcommits.org/en/v1.0.0/#examples

Before you ask for review:
- Formatting, lint, type checks and the relevant fast tests pass locally or in CI.
  Reviewers shouldn't spend time on things the tooling catches.
- You can explain the change, how it behaves and how it fails. AI-assisted work is
  fine, but you own the result, including this description.
- The diff is under ~400 changed lines. If it isn't, split it into stacked PRs that
  each ship safely on their own, or say below why it can't be split.

Sections marked (if applicable) can be deleted when they don't apply.
-->

## What and why

<!--
What changes and why. Link the ticket and any design doc.
Describe the user-visible or system behaviour that changes.
If this is part of a stack, link the PR it builds on.
-->

## Edge cases and failure modes

<!--
Which edge cases did you consider? What happens when a dependency is slow, down,
or returns something unexpected: fail fast, retry, degrade, or surface an error?
-->

## Testing

<!--
What the automated tests cover. Unit tests should cover the changed behaviour and
its key edge cases, and assert behaviour rather than implementation.
-->

### How to test

<!--
Steps for a reviewer to verify the change locally or on the review app.
-->

### Screenshots or video (if applicable)

<!--
For UI changes, add screenshots or a short video.

| Before | After |
| ------ | ----- |
| -      | -     |
-->

## Rollout and rollback

<!--
- Blast radius: who or what is affected if this goes wrong?
- Rollout: feature flag, staged rollout, or straight deploy?
- Rollback: how do we undo it, and is anything not safely reversible?
- Data changes (migrations, backfills, schema): compatible with the code already
  running, and can it be reversed?
- Staging: what you validated there, and any difference from production that matters.
-->

## What to watch

<!--
Metrics, logs, traces, alerts and user impact to watch during rollout, and what
"bad" looks like.
-->

## Post-deploy smoke test

<!--
The check that proves the user-visible or system-critical path still works after
deploy. Automated or manual. Required for any non-trivial production change.
-->

## Observability and reliability (if applicable)

<!-- For PRs that add or change calls to other services, event handlers or jobs. -->

- [ ] Downstream calls emit metrics and traces: which dependency, how often it fails, how long it takes, and what triggered the call
- [ ] Correlation IDs propagate across service boundaries, and event-driven flows record causation where useful
- [ ] Event handlers are idempotent with bounded, observable retries, or this PR explains why not
- [ ] Dead-letter / poison-message behaviour is understood for critical flows
