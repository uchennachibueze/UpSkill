# 2-Week DevOps Refresher Plan

## Goal
Rebuild speed, confidence, and hands-on fluency across the core tools you already know while sharpening the areas that will move you toward senior-level platform engineering.

## How To Use This Plan
- Spend `60 to 90 minutes` per day on weekdays.
- Spend `2 to 3 hours` on weekend practical sessions.
- Follow this pattern for each topic:
  - read the official overview
  - complete the quickstart or lab
  - repeat the core steps from memory
  - write down what broke and how you fixed it

## Week 1

### Day 1: Linux Refresher
Focus:
- processes
- services
- permissions
- logs
- networking basics

Resources:
- [Linux Foundation LFS101](https://training.linuxfoundation.org/training/introduction-to-linux/)

Hands-on:
- inspect running processes
- restart a service
- review logs
- create users, groups, and file permissions in a lab VM or container

Output:
- one page of Linux command notes

### Day 2: Git Refresher
Focus:
- branching
- rebasing
- merge conflicts
- tags
- pull request flow

Resources:
- [Git Tutorial](https://git-scm.com/docs/gittutorial)
- [Git Workflows](https://git-scm.com/docs/gitworkflows)

Hands-on:
- create a feature branch
- make conflicting edits
- resolve the conflict manually
- tag a release

Output:
- short note on your preferred Git workflow

### Day 3: Terraform Core
Focus:
- providers
- resources
- variables
- outputs
- state

Resources:
- [Terraform Tutorials](https://developer.hashicorp.com/terraform/tutorials)
- [Terraform CLI Fundamentals](https://developer.hashicorp.com/terraform/tutorials/cli)

Hands-on:
- write a small Terraform config
- run `init`, `plan`, and `apply`
- inspect the state file

Output:
- one simple reusable Terraform module

### Day 4: Terraform Structure and Multi-Environment Thinking
Focus:
- module structure
- remote state
- environment separation
- input conventions

Resources:
- [Terraform Documentation](https://developer.hashicorp.com/terraform)

Hands-on:
- split a config into modules
- model `dev` and `prod`
- document backend and variable strategy

Output:
- starter layout for `modules`, `dev`, and `prod`

### Day 5: Docker
Focus:
- images
- layers
- Dockerfiles
- registry workflow
- local troubleshooting

Resources:
- [Docker Get Started](https://docs.docker.com/get-started/)
- [Docker Hands-on Lab](https://docs.docker.com/guides/lab-container-getting-started/)

Hands-on:
- build an image
- run it locally
- inspect logs
- reduce image size where possible

Output:
- one working Dockerfile with notes on layer optimization

### Day 6: Kubernetes Core
Focus:
- pods
- deployments
- services
- configmaps
- secrets
- `kubectl` troubleshooting

Resources:
- [Kubernetes Basics](https://kubernetes.io/docs/tutorials/kubernetes-basics/)

Hands-on:
- deploy a sample app
- scale it
- update the image
- inspect pods and events

Output:
- one cheat sheet of the `kubectl` commands you use most

### Day 7: Kubernetes Networking and Operations
Focus:
- ingress
- namespaces
- resource limits
- autoscaling
- rollout and rollback

Resources:
- [Kubernetes Basics](https://kubernetes.io/docs/tutorials/kubernetes-basics/)
- [AKS Documentation](https://learn.microsoft.com/azure/aks/)

Hands-on:
- create namespaces
- add limits
- test rollout and rollback
- review ingress flow

Output:
- short note on common Kubernetes failure signals

## Week 2

### Day 8: AKS Refresh
Focus:
- cluster creation
- ACR integration
- RBAC
- monitoring

Resources:
- [AKS Documentation](https://learn.microsoft.com/azure/aks/)
- [AKS Cluster Tutorial](https://learn.microsoft.com/en-us/azure/aks/tutorial-kubernetes-deploy-cluster)

Hands-on:
- deploy or review an AKS cluster
- connect `kubectl`
- review node pools and monitoring options

Output:
- AKS build checklist

### Day 9: Azure Pipelines and Azure Policy
Focus:
- pipeline stages
- service connections
- approvals
- governance controls

Resources:
- [Azure Pipelines Documentation](https://learn.microsoft.com/en-us/azure/devops/pipelines/)
- [Intro to Azure Policy](https://learn.microsoft.com/en-us/learn/modules/intro-to-azure-policy/)

Hands-on:
- create a simple YAML pipeline
- add validation and approval thinking
- review how policy blocks noncompliant resources

Output:
- draft CI/CD pipeline flow for Azure

### Day 10: AWS IAM, Organizations, and Identity Center
Focus:
- IAM roles
- account structure
- organization hierarchy
- centralized access

Resources:
- [Getting Started with IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/getting-started.html)
- [Getting Started with AWS Organizations](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_getting-started.html)
- [Getting Started with IAM Identity Center](https://docs.aws.amazon.com/singlesignon/latest/userguide/getting-started.html)

Hands-on:
- map out a `shared`, `dev`, `staging`, `prod` account structure
- define example admin and read-only roles
- write notes on permission sets and centralized access

Output:
- AWS landing zone sketch

### Day 11: EKS Refresh
Focus:
- cluster architecture
- worker nodes
- networking
- authentication
- workload deployment

Resources:
- [Get Started with Amazon EKS](https://docs.aws.amazon.com/eks/latest/userguide/getting-started.html)

Hands-on:
- review cluster creation flow
- deploy a sample application
- inspect node groups and access patterns

Output:
- AKS vs EKS comparison note

### Day 12: GitHub Actions and GitOps
Focus:
- workflow triggers
- jobs
- artifacts
- deployment flow
- GitOps concepts

Resources:
- [GitHub Actions Documentation](https://docs.github.com/en/actions/automating-your-workflow-with-github-actions)
- [Understanding GitHub Actions](https://docs.github.com/en/actions/get-started/understanding-github-actions)
- [Argo CD Getting Started](https://argo-cd.readthedocs.io/en/release-3.1/getting_started/)

Hands-on:
- create a basic CI workflow
- define a deployment workflow idea
- install or review Argo CD flow

Output:
- simple CI pipeline plus GitOps notes

### Day 13: Observability
Focus:
- metrics
- dashboards
- logs
- traces
- alerting

Resources:
- [Prometheus Getting Started](https://prometheus.io/docs/tutorials/getting_started/)
- [Grafana Getting Started](https://grafana.com/docs/grafana/latest/getting-started/)
- [OpenTelemetry Getting Started](https://opentelemetry.io/docs/getting-started/)

Hands-on:
- scrape one target with Prometheus
- create one Grafana dashboard
- review how traces fit into system visibility

Output:
- mini observability stack notes

### Day 14: Policy and Security Refresh
Focus:
- admission control
- scanning
- policy-as-code
- platform guardrails

Resources:
- [Kyverno Quick Start](https://kyverno.io/docs/introduction/quick-start/)

Hands-on:
- review a sample policy
- think through blocking `latest` tags and privileged containers
- connect this to your future capstone

Output:
- list of five platform policies you want in your capstone

## End-of-Week Practical Challenge
At the end of Week 2, do a mini build:
- write a small app or use a sample one
- containerize it
- deploy it with Kubernetes
- create a simple CI workflow
- add one dashboard or one alert

## Success Criteria
By the end of these 2 weeks, you should be able to:
- explain the purpose of each core tool without hesitation
- rebuild a basic environment from memory
- compare AKS and EKS at a practical level
- describe a modern GitOps delivery flow
- discuss observability and policy-as-code with more confidence

## What To Do Next
After this refresher, transition immediately into the multi-cloud capstone:
- Week 3 onward: AWS depth, GitOps, platform engineering, SRE, and governance

