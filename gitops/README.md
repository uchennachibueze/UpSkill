# GitOps

Use this area for Argo CD application definitions and cluster bootstrap resources.

Recommended structure:
- `clusters/` for per-cluster bootstrap
- `apps/` for application definitions

Keep promotion explicit and auditable across `dev`, `staging`, and `prod`.

