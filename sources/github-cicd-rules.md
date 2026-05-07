# Source: github_cicd_rule.md

## Summary
This document defines the development workflow for the Travery Backend team. It emphasizes collaboration, code quality, and automated deployment through GitHub.

Highlights include:
- **Branching Strategy**: Use of `feature/`, `bugfix/`, and `chore/` branches, with `test` for integration and `main` for production.
- **Commit Standards**: Enforces [[conventional-commits]] format (e.g., `feat:`, `fix:`) and encourages small, frequent commits.
- **Pull Request (PR) Process**: Mandates PRs for all changes, requiring CI passes and team approvals before merging.
- **CI/CD Pipeline**: Automates formatting checks, testing, and deployment to production servers upon merging to `main`.
- **Emergency Procedures**: Guidelines for Hotfixes and critical production bugs.
- **Versioning**: Adopts Semantic Versioning (`MAJOR.MINOR.PATCH`).

## Identified Entities
- **Organizations**: [[travery]]
- **Concepts**: [[ci-cd-pipeline]], [[conventional-commits]], Pull Request, Hotfixes, Semantic Versioning
