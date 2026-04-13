# cka-shared

Shared bridge between:
- `cka-qa` for theory, quizzes, repetition, and progress tracking
- `cka-lab` for practical work, manifests, kubectl drills, and troubleshooting labs

## Contract

Primary file:
- `handoff.json`

## Ownership

- `cka-qa` updates `theoryStatus` and `practicalFocus`
- `cka-lab` updates `practicalFeedback`
- both may refresh `lastUpdated`

## Design rule

Keep this small, explicit, and machine-readable. Do not turn it into a second memory system.
