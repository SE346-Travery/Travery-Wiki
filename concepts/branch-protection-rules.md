---
title: "Branch Protection Rules"
category: concepts
tags: [git, github, security]
sources: [deployment-guide, github-cicd-rules]
updated: 2026-05-06
---

# Concept: Branch Protection Rules

## Definition
Technical enforcements set within GitHub to protect core branches ([[main]], [[test]]) from unverified or malicious changes.

## Enabled Rules
- **Require a pull request before merging**: No direct pushes allowed.
- **Require status checks to pass before merging**: Links the [[CI Pipeline]] status to the merge button.
  - Mandatory checks: "Format & Import Check", "Build & Run Tests".
- **Dismiss stale pull request approvals**: Revokes approval if new commits are pushed to the branch.
- **Do not allow bypassing settings**: Even administrators must follow the rules.

## Purpose
Acts as an automated "gatekeeper" to ensure all code in production has been formatted, tested, and reviewed by the team.

## References
- [[github-cicd-rules]]
- [[deployment-guide]]
