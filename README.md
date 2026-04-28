# Multi-Cloud Platform Engineering Capstone

## Purpose
This repository is the implementation home for a senior-level DevOps and platform engineering capstone across Azure and AWS.

It is designed to demonstrate practical experience in:
- platform engineering
- DevSecOps
- infrastructure as code
- Kubernetes operations
- GitOps
- observability
- resilience engineering
- cost governance

## Project Summary
You will build the same production-style platform on both clouds:
- Azure version using `AKS`, `Azure Policy`, `Key Vault`, `Azure Monitor`, and supporting network/security services
- AWS version using `EKS`, `AWS Organizations`, `IAM Identity Center`, `Secrets Manager`, `CloudWatch`, and supporting network/security services

The business scenario is a regulated microservices platform for an e-commerce or EMR-style workload with:
- private networking
- controlled ingress
- CI/CD
- GitOps promotion
- secrets management
- policy enforcement
- centralized observability
- backup and recovery planning

## Repository Roadmap
- [30-60-90 Day Plan](./docs/30-60-90-day-plan.md)
- [Resume and LinkedIn Packaging](./docs/resume-linkedin-packaging.md)
- [Azure Architecture](./docs/architecture/azure-architecture.md)
- [AWS Architecture](./docs/architecture/aws-architecture.md)
- [Runbooks Guide](./docs/runbooks/README.md)
- [ADR Guide](./docs/adr/README.md)

## Suggested Delivery Order
1. Establish architecture, naming, and governance model.
2. Build landing zones and shared services.
3. Stand up AKS and EKS platform baselines.
4. Add CI/CD, GitOps, and security controls.
5. Add observability, reliability testing, and cost governance.
6. Package the implementation as a resume-ready senior platform engineering project.

## Initial Folder Map
```text
multi-cloud-platform-engineering-capstone/
  docs/
    architecture/
    runbooks/
    adr/
  terraform/
    azure/
    aws/
    modules/
  kubernetes/
    base/
    overlays/
  gitops/
    apps/
    clusters/
  observability/
    grafana/
    alerts/
  security/
    policies/
    scans/
  services/
    frontend/
    api/
    worker/
```

## Evidence You Should Capture
Keep proof as you build:
- architecture diagrams
- pull requests
- Terraform plans
- pipeline screenshots
- dashboard screenshots
- policy failures and remediations
- incident drill notes
- cost optimization notes

## Recommended Outcome
By the end of this capstone, you should be able to present yourself as an engineer who can:
- design landing zones
- build secure multi-environment pipelines
- run Kubernetes platforms on Azure and AWS
- implement GitOps and policy enforcement
- operate systems with SRE-style observability and resilience practices

