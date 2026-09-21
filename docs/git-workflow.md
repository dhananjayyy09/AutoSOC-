# Git Workflow

We use a feature-branch workflow.

## Branches

### `main`
- The production-ready state of the platform.
- Merges to `main` should only come from `develop` via Pull Request after rigorous testing.

### `develop`
- The active integration branch.
- Developers branch off `develop` and merge back into `develop` via Pull Request.

### Feature Branches
Currently assigned active feature branches for the core team:
- `feature/dj-foundation`: Backend architecture, AI infrastructure, DevOps setup.
- `feature/pranjal-security-data`: Detection logic, threat intelligence integration, evaluation.
- `feature/shreyash-frontend`: Dashboard implementation, UX/UI, visualization.

## Workflow Rules
1. Never commit directly to `main` or `develop`.
2. Do not force-push to shared branches.
3. Do not modify or push to another developer's active feature branch without coordination.
4. Keep commits atomic and messages descriptive.
