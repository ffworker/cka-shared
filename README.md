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

## Broader workflow

### QA -> Shared
`cka-qa` writes:
- `theoryStatus`
- `practicalFocus`

### Lab -> Shared
`cka-lab` writes:
- `practicalFeedback`

### Shared -> QA and Lab
Both repos must read this file before planning work so theory and practice stay aligned.

## Submodule rule

In both parent repos, `cka-shared` is a git submodule.
If `handoff.json` changes:
1. commit and push inside `cka-shared`
2. commit the updated submodule pointer in the parent repo
