# AWS Architecture

## Objective
Build a production-style AWS platform for the same regulated workload using multi-account governance, secure networking, EKS, GitOps, observability, and resilience patterns.

## Architecture Layers
- organization and identity
- network and ingress
- platform shared services
- Kubernetes workloads
- observability and security
- data and messaging
- CI/CD and GitOps

## Detailed AWS Resource Landscape

```mermaid
flowchart TB
    DEV["Developers"] --> SCM["GitHub Repos"]
    SCM --> PIPE["CI Pipelines"]
    PIPE --> SCAN["Unit Tests / Trivy / Checkov / Terraform Validate"]
    SCAN --> ECR["Amazon ECR"]
    SCAN --> STATE["Terraform State"]
    PIPE --> APPLY["Approved Terraform Apply"]

    APPLY --> ORG["AWS Organizations"]
    ORG --> SHARED["Shared Services Account"]
    ORG --> DEVACC["Dev Account"]
    ORG --> STGACC["Staging Account"]
    ORG --> PRDACC["Prod Account"]

    SHARED --> IAM["IAM Identity Center / Central Audit"]
    SHARED --> SEC["CloudTrail / Config / GuardDuty / Security Hub"]
    SHARED --> SCP["Service Control Policies"]

    DEVACC --> VPC1["Dev VPC"]
    STGACC --> VPC2["Staging VPC"]
    PRDACC --> VPC3["Prod VPC"]

    VPC1 --> EKS1["EKS Dev"]
    VPC2 --> EKS2["EKS Staging"]
    VPC3 --> EKS3["EKS Prod"]

    EKS1 --> ARGO["Argo CD"]
    EKS2 --> ARGO
    EKS3 --> ARGO

    EKS1 --> ESO["External Secrets / IRSA"]
    EKS2 --> ESO
    EKS3 --> ESO

    ESO --> SM["Secrets Manager / SSM / KMS"]

    EKS3 --> ING["ALB Ingress / cert-manager / external-dns"]
    EKS3 --> APPS["Frontend / API / Worker Services"]
    EKS3 --> DATA["RDS PostgreSQL / ElastiCache Redis"]
    EKS3 --> MSG["SQS / SNS / EventBridge"]

    EKS1 --> OBS["Prometheus / Grafana / Loki / CloudWatch / OTEL"]
    EKS2 --> OBS
    EKS3 --> OBS

    OBS --> ALERT["Alerts / SLOs / Incident Response"]
```

## Recommended AWS Services
- `AWS Organizations`
- `IAM Identity Center`
- `CloudTrail`
- `AWS Config`
- `GuardDuty`
- `Security Hub`
- `VPC`
- `EKS`
- `ECR`
- `Secrets Manager`
- `KMS`
- `RDS PostgreSQL`
- `ElastiCache Redis`
- `CloudWatch`
- `SQS`, `SNS`, or `EventBridge`

## Senior Design Decisions To Practice
- separate shared services, audit, and workload concerns by account
- enforce least privilege with role assumptions and scoped automation roles
- use IRSA for Kubernetes workloads
- centralize security and audit visibility
- make production changes auditable and approval-driven

## Portfolio Artifacts To Capture
- account architecture diagram
- VPC and subnet segmentation diagram
- EKS baseline module layout
- SCP and identity model notes
- security findings and remediations
- dashboard and incident drill evidence

