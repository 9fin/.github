<!--
Title: start with a conventional commit prefix (feat:, fix:, chore: ...).
See https://www.conventionalcommits.org/en/v1.0.0/#examples

Tick what applies and delete what doesn't. Sections marked (if applicable) can go.
-->

## Before ready for review

- [ ] Formatting, lint, type checks and the relevant fast tests pass locally or in CI
- [ ] I can explain the change, how it behaves and how it fails. AI-assisted is fine, but I own it, this description included
- [ ] The diff is under ~400 changed lines, or it's split into stacked PRs, or I've said below why it can't be split

## What and why

Ticket: <!-- e.g. ENG-123 -->

<!-- What changes, why, and which user-visible or system behaviour moves. Link any design doc. -->

## Edge cases and failure modes

- [ ] I've listed the edge cases I considered
- [ ] I've said what happens when a dependency is slow, down or returns junk: fail fast, retry, degrade, or surface an error

<!-- Notes -->

## Testing

- [ ] Unit tests cover the changed behaviour and its main edge cases
- [ ] Tests assert behaviour, not implementation
- [ ] Integration tests cover any query, migration or service boundary change

### How to test

<!-- Steps for a reviewer to check this locally or on the review app. -->

### Screenshots or video (if applicable)

<!--
| Before | After |
| ------ | ----- |
| -      | -     |
-->

## Rollout

- [ ] Blast radius: I've noted who or what is hit if this goes wrong
- [ ] Rollout method: feature flag, staged rollout, or straight deploy
- [ ] Staging: I've said what I checked there and any difference from production that matters

<!-- Notes -->

## Rollback

- [ ] I've written how to undo this (revert, flag off, something else)
- [ ] Anything that can't be safely reversed is called out
- [ ] Data changes (migrations, backfills, schema) work with the code already running and can be reversed

<!-- Notes -->

## What to watch

- [ ] I've listed the metrics, logs, traces or alerts to watch during rollout, and what "bad" looks like

<!-- Notes -->

## Post-deploy smoke test

<!--
Needed when the change can affect production behaviour: application code, config,
infra, dependencies, migrations. Skip it for docs, comments, test-only and dev
tooling changes, and tick the last box instead.
-->

- [ ] I've written the check that proves the user-visible or system-critical path still works after deploy (automated or manual)
- [ ] Not needed: this PR can't change production behaviour

## Observability and reliability (if applicable)

<!-- For PRs that add or change calls to other services, event handlers or jobs. -->

- [ ] Downstream calls emit metrics and traces: which dependency, how often it fails, how long it takes, and what triggered the call
- [ ] Correlation IDs propagate across service boundaries, and event-driven flows record causation where useful
- [ ] Event handlers are idempotent with bounded, observable retries, or this PR explains why not
- [ ] Dead-letter / poison-message behaviour is understood for critical flows
