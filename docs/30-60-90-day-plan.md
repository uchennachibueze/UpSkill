# 30-60-90 Day Execution Plan

## Objective
Use 90 days to build a senior-level multi-cloud platform engineering capstone with enough depth to strengthen your real-world DevOps instincts and give you strong interview material.

## Days 1-30: Foundation and Landing Zones

### Focus
- architecture
- standards
- governance
- cloud foundations
- baseline Kubernetes setup

### Outcomes
- project scope locked
- repo structure created
- Azure landing zone baseline deployed
- AWS landing zone baseline deployed
- AKS and EKS clusters provisioned

### Deliverables
- architecture decision records
- network diagrams
- naming and tagging standards
- Terraform backend and module structure
- Azure management group and policy model
- AWS organization and account model
- baseline AKS and EKS deployment notes

### Weekly breakdown

#### Week 1
- define the regulated workload scenario
- choose service boundaries
- document `dev`, `staging`, `prod` environment model
- define identity, RBAC, and secrets strategy
- write first draft of architecture diagrams

#### Week 2
- implement Azure shared services
- create network segmentation
- deploy Key Vault, ACR, monitoring workspace, and AKS baseline
- enforce tagging and region restrictions with Azure Policy

#### Week 3
- implement AWS shared services
- create account and VPC strategy
- deploy ECR, EKS baseline, audit logging, and identity model
- enforce guardrails with SCPs and security services

#### Week 4
- stabilize Terraform modules
- document bootstrap steps
- create cluster baseline checklist
- capture screenshots and notes for portfolio evidence

### Senior habits to practice
- document tradeoffs
- record assumptions
- treat governance as part of platform design, not an afterthought

## Days 31-60: Delivery, GitOps, and DevSecOps

### Focus
- CI/CD
- GitOps
- security scanning
- policy-as-code
- secure workload delivery

### Outcomes
- pipelines running
- GitOps promotion flow established
- secure image and IaC scanning gates enforced
- namespaces and workload guardrails standardized

### Deliverables
- GitHub Actions pipeline or Azure DevOps pipeline
- Argo CD deployment model
- Helm or Kustomize overlays
- image scanning reports
- IaC scanning reports
- policy pack using Kyverno or Gatekeeper

### Weekly breakdown

#### Week 5
- build CI pipelines for Terraform and app delivery
- add validation, linting, and security scanning
- configure approval gates for production

#### Week 6
- deploy Argo CD
- define app-of-apps or cluster bootstrap pattern
- implement release promotion workflow across environments

#### Week 7
- add secrets integration with workload identity
- implement admission control policies
- block insecure images and Kubernetes misconfigurations

#### Week 8
- harden namespaces, quotas, and network policies
- document rollback model
- run failed deployment simulations and recoveries

### Senior habits to practice
- make release paths boring and repeatable
- force security and quality controls before production
- define rollback before scale

## Days 61-90: Observability, Resilience, and Executive Packaging

### Focus
- SRE
- incident response
- disaster recovery
- cost governance
- project packaging

### Outcomes
- full observability stack operating
- SLOs and alerts documented
- incident and restore drills completed
- resume and LinkedIn materials ready

### Deliverables
- Grafana dashboards
- Prometheus and logging setup
- service health views
- incident runbooks
- backup and restore notes
- cost optimization report
- final diagrams
- final project README

### Weekly breakdown

#### Week 9
- instrument at least one service with OpenTelemetry
- create golden signal dashboards
- define service alerts and escalation notes

#### Week 10
- run failure scenarios
- test backup and restore approach
- rotate a secret and validate no outage
- write incident response runbooks

#### Week 11
- review node sizing, requests, limits, and storage choices
- add cost governance notes and tagging dashboard
- compare Azure and AWS design tradeoffs

#### Week 12
- finalize architecture diagrams
- prepare project walkthrough
- write resume bullets and STAR stories
- publish or organize proof artifacts

### Senior habits to practice
- speak in terms of reliability, governance, and tradeoffs
- quantify impact where possible
- explain what you would improve next, not just what you built

## Success Criteria
- both clouds deploy from code with minimal manual work
- production promotion requires policy checks and approvals
- workloads use secure secrets flow
- dashboards show useful health signals
- at least one incident drill and one restore drill are documented
- project packaging is strong enough to discuss in interviews

