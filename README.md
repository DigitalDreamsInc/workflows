<!--

********************************************************************************

WARNING:

    DO NOT EDIT "workflows/README.md"

    IT IS PARTIALLY AUTO-GENERATED

    (based on reusable workflow files and usage examples)

********************************************************************************

-->

# Quick reference

- **Maintained by**:  
  [Douglas Cabrera](https://github.com/cabrera-evil)

- **Where to get help**:  
  [GitHub Issues](https://github.com/cabrera-evil/workflows/issues)

# What is workflows?

**workflows** is a curated collection of reusable GitHub Actions workflows designed to standardize CI/CD pipelines across multiple repositories. Each workflow is modular, version-controlled, and production-ready, making it easy to compose consistent automation logic for testing, building, deploying, and more.

These workflows follow GitHub’s [reusable workflow model](https://docs.github.com/en/actions/using-workflows/reusing-workflows) and are designed for flexibility, extensibility, and easy integration.

# How to use these workflows

In any repository where you want to reuse a workflow:

```yaml
# .github/workflows/ci.yml
name: CI

on:
  push:
    branches: [main]

jobs:
  analyze:
    uses: cabrera-evil/workflows/.github/workflows/code-analysis.yaml@main
    with:
      node-version: 20
```

> Replace `code-analysis.yaml` with the workflow you want to use.
> Pin to a specific commit or tag in production environments.

# Available workflows

| Workflow File                | Purpose                                                            |
| ---------------------------- | ------------------------------------------------------------------ |
| `code-analysis.yaml`         | Run static analysis (e.g., ESLint, TypeScript, format checks)      |
| `container-analysis.yaml`    | Analyze Dockerfile or image vulnerabilities using Trivy            |
| `deploy-helm.yaml`           | Deploy Helm charts to Kubernetes clusters                          |
| `deploy-k8s.yaml`            | Apply raw Kubernetes manifests using `kubectl`                     |
| `deploy-vercel.yaml`         | Trigger Vercel deployment using token and team/project info        |
| `deps-analysis.yaml`         | Analyze dependencies using tools like `npm audit`, `osv-scanner`   |
| `notify-status-discord.yaml` | Send job status notifications to Discord via webhook               |
| `prisma-migrate.yaml`        | Run Prisma database migrations                                     |
| `publish-docker.yaml`        | Build and push Docker images to Docker Hub or GitHub Packages      |
| `publish-npm.yaml`           | Publish JavaScript packages to NPM registry                        |
| `register-deployment.yaml`   | Register a deployment in GitHub to be tracked in UI/metrics        |
| `semantic-release.yaml`      | Automate versioning and changelog generation with semantic-release |
| `set-deployment-status.yaml` | Mark a deployment as success/failure in GitHub                     |
| `set-environment.yaml`       | Set dynamic environment variables at runtime or per context        |

> Each workflow is self-documented via `inputs:` and `secrets:` in the YAML header.

# License

This project is released under the [MIT License](LICENSE).
