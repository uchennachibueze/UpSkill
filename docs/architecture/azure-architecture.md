# Azure Architecture

## Objective
Build a production-style Azure platform for a regulated microservices workload using governance-first design, secure networking, AKS, GitOps, observability, and resilience patterns.

## Architecture Layers
- governance and identity
- network and ingress
- platform shared services
- Kubernetes workloads
- observability and security
- data and messaging
- CI/CD and GitOps

## Detailed Azure Resource Landscape

```mermaid
flowchart TB
    DEV["Developers"] --> SCM["GitHub / Azure DevOps Repos"]
    SCM --> PIPE["CI Pipelines"]
    PIPE --> SCAN["Unit Tests / Trivy / Checkov / Terraform Validate"]
    SCAN --> ACR["Azure Container Registry"]
    SCAN --> STATE["Terraform State"]
    PIPE --> APPLY["Approved Terraform Apply"]

    APPLY --> MG["Management Groups"]
    MG --> SUBS["Subscriptions: Shared / Dev / Staging / Prod"]
    SUBS --> POL["Azure Policy / RBAC / Defender for Cloud"]

    SUBS --> HUB["Hub VNet"]
    HUB --> DNS["Private DNS"]
    HUB --> FW["Azure Firewall / NSGs / UDRs"]
    HUB --> BASTION["Bastion / Access Control"]

    HUB --> SPOKEDEV["Dev Spoke"]
    HUB --> SPOKESTG["Staging Spoke"]
    HUB --> SPOKEPRD["Prod Spoke"]

    SPOKEDEV --> AKSDEV["AKS Dev"]
    SPOKESTG --> AKSSTG["AKS Staging"]
    SPOKEPRD --> AKSPRD["AKS Prod"]

    AKSDEV --> ARGO["Argo CD"]
    AKSSTG --> ARGO
    AKSPRD --> ARGO

    AKSDEV --> ESO["External Secrets / Workload Identity"]
    AKSSTG --> ESO
    AKSPRD --> ESO

    ESO --> KV["Azure Key Vault"]

    AKSPRD --> ING["Ingress Controller + cert-manager + external-dns"]
    AKSPRD --> APPS["Frontend / API / Worker Services"]
    AKSPRD --> DATA["Azure Database for PostgreSQL / Azure Cache for Redis"]
    AKSPRD --> MSG["Service Bus / Event Grid"]

    AKSDEV --> OBS["Azure Monitor / Managed Prometheus / Grafana / Loki"]
    AKSSTG --> OBS
    AKSPRD --> OBS

    OBS --> ALERT["Alerts / SLOs / Incident Response"]
```

## Recommended Azure Services
- `Management Groups`
- `Azure Policy`
- `Microsoft Entra ID` and RBAC
- `Azure Key Vault`
- `Azure Container Registry`
- `AKS`
- `Azure Monitor`
- `Managed Prometheus` and `Managed Grafana` if desired
- `Azure Database for PostgreSQL`
- `Azure Cache for Redis`
- `Service Bus` or `Event Grid`
- `Private DNS`
- `Azure Firewall`

## Senior Design Decisions To Practice
- separate shared services from workload environments
- default to private endpoints where sensible
- use workload identity instead of embedded credentials
- centralize logging and policy enforcement
- keep production promotion gated and observable

## Portfolio Artifacts To Capture
- management group and subscription model diagram
- network segmentation diagram
- AKS baseline module layout
- policy definitions and assignments
- Grafana screenshots
- incident and restore drill notes

