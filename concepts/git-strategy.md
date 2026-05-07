# Concept: Git Strategy (GitHub Flow)

## Definition
The branching and collaboration model used by the [[travery]] development team to ensure code stability and streamlined delivery.

## Branching Model
- **`main` (Production)**: The state of the live system. Only code merged from `test` enters here.
- **`test` (Integration)**: Where features are combined and verified for stability. No direct code is written here.
- **`feature/*`, `bugfix/*`, `chore/*`**: Short-lived branches where individual developers work. Created from the latest `test` branch.

## Workflow
1. Developer creates a branch from `test`.
2. Developer commits changes following [[conventional-commits]].
3. Pull Request (PR) is opened targeting `test`.
4. [[ci-cd-pipeline]] runs tests and formatting checks.
5. Peer review is conducted.
6. Once approved and CI passes, it is merged into `test`.
7. Periodically, `test` is merged into `main` via a Release PR, triggering the [[ci-cd-pipeline]].

## Safeguards
- **[[branch-protection-rules]]**: Enforce PR requirements, status checks, and prevent direct pushes to `main` or `test`.

## References
- [[github-cicd-rules]]
- [[deployment-guide]]
