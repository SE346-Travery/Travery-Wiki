# Concept: CI/CD Pipeline

## Definition
The automated process of integrating and deploying code changes in the [[travery]] backend, emphasizing code quality and stability through GitHub Actions.

## Branching Strategy
- **`feature/`**, **`bugfix/`**, **`chore/`**: Developer work branches created from `test`.
- **`test`**: Integration branch for team validation. No automatic deployment.
- **`main`**: Production branch. Code is deployed automatically to the production server upon merge.

## Workflow
1. **Pull Request to `test`**:
   - Triggers **CI Pipeline**: Auto-formatting (Spotless), Build, and Unit Testing.
   - Requires at least 1 team approval and passing CI checks to merge.
2. **Pull Request from `test` to `main`**:
   - Triggers **CI Pipeline** with additional **Docker Build** and **Push to GHCR**.
3. **Merge to `main`**:
   - Triggers **CD Pipeline**: Automated deployment to Server 1, image pull, and container restart.

## Commit Standards
Follows [[conventional-commits]] (e.g., `feat:`, `fix:`). Encourages small, logical commits for easier review.

## References
- [[github-cicd-rules]]
- [[travery-backend]]
