# Seed question banks by topic

These are starting points, not the universe. Generate fresh scenarios from `references/question-patterns.md` when the seeds feel stale or don't match the requested intersection of topic × level × tier.

Each entry has a difficulty marker: **[J]** junior · **[M]** mid · **[S]** senior · **[ST]** staff+.

---

## Kubernetes

- **[J]** Pods are in `Pending`. Walk me through what to check.
- **[J]** A Deployment rollout is stuck. Where do you start?
- **[M]** Your StatefulSet is stuck `Pending` after a node went away. Debug it.
- **[M]** HPA is scaling pods to the max but p99 latency keeps rising. What's wrong?
- **[M]** You need to roll out a breaking change to a service deployed via Argo CD across 50 clusters. Plan it.
- **[S]** Design a multi-tenant K8s platform for 30 internal teams. They want isolation, autoscaling, and self-service.
- **[S]** A single namespace is consuming 80% of your cluster's CPU. The team owning it isn't responsive. What do you do?
- **[S]** You're upgrading a 200-cluster fleet from K8s 1.27 → 1.30. Plan the rollout. What's your blast-radius unit?
- **[ST]** Your org runs K8s for 5000 engineers. CRDs are sprawling. Argue for or against a CRD platform team and explain how you'd pitch it to leadership.
- **[ST]** Make the case for or against running Kafka on Kubernetes for your org's primary stream-processing workload.

## AWS

- **[J]** EC2 instance is "running" but you can't SSH. Walk through the debug.
- **[J]** Your S3 bucket should be private but `aws s3 ls` from anywhere works. What do you check?
- **[M]** RDS Aurora instance is at 100% CPU at 10am every weekday. Why? What do you do?
- **[M]** Lambda function intermittently times out. Same code, same input. Find it.
- **[M]** Cost on a single ALB jumped 5x last month. Investigate.
- **[S]** Design a multi-region active-active payments API on AWS. RTO 30s, RPO 0.
- **[S]** Your org spends $4M/year on AWS, 60% on EC2, 30% on data transfer, 10% on RDS. Where do you start cutting?
- **[S]** You have to migrate from EKS to a managed K8s offering you don't know yet (the company picked it). 200 services, 30 engineers, 8 weeks. Plan it.
- **[ST]** Argue for or against AWS Organizations + Control Tower for a 50-account, 8-team org with mixed compliance needs (some SOC2, some HIPAA).
- **[ST]** You're advising a CTO on whether to leave AWS for a multi-cloud setup. What's your recommendation framework?

## Docker

- **[J]** Your container exits immediately after starting. What's the first thing you check?
- **[J]** Your image is 4GB. The team across the hall has a similar service in 200MB. What's likely happening?
- **[M]** Build is slow because you keep busting cache on every push. Walk through how to fix.
- **[M]** Your container works locally but `OOMKilled`s in prod. The "memory" footprint looks similar. Why?
- **[S]** Argue for or against multi-stage builds for a Go monorepo with 40 services.
- **[S]** Your team uses Dockerfile-per-service. Image build matrix is now 90 minutes in CI. Plan a fix.

## Terraform

- **[J]** `terraform plan` says it'll destroy your prod RDS. You didn't touch RDS. What do you do?
- **[J]** State file is locked. The lock entry is 6 hours old. Action?
- **[M]** Refactor a 3000-line `main.tf` into something 30 engineers can work in without stepping on each other.
- **[M]** A team imported a manually-created VPC into Terraform. Now plans show drift on a security group. Walk through the fix.
- **[M]** Module versioning strategy for a 12-module internal Terraform Registry. Explain.
- **[S]** Compare Terraform vs Pulumi vs CDK for a Python-heavy 60-engineer infra org. What do you pick and why?
- **[S]** Design a CI/CD pipeline that runs `terraform plan` on PRs without leaking state to forks and without requiring per-PR cloud credentials.
- **[ST]** You're asked to standardize IaC across 8 acquired companies, 5 different tools (Terraform, CloudFormation, Pulumi, raw scripts, ClickOps). Six-month plan.

## CI/CD

- **[J]** A test passes locally and fails in CI. Where do you start?
- **[J]** Your pipeline takes 45 minutes. Pick three places you'd look first to cut it.
- **[M]** Your team has 200 GitHub Actions workflows. Maintenance is taking 1 engineer-day per week. What do you change?
- **[M]** Migrate a Jenkins-on-VMs setup to a SaaS CI without a freeze. 30 engineers, 200 pipelines.
- **[S]** Design CI/CD for a 50-service polyrepo where teams want autonomy but security wants centralized scanning.
- **[S]** Argue for or against trunk-based development for a 100-engineer org currently on long-lived feature branches.
- **[ST]** Your CI cost is $80k/month and rising 15% MoM. Lay out the audit, the cuts, and the org change you'd push for.

## Linux

- **[J]** A process is using "too much memory". Walk me through how you'd actually verify that and decide if it's a problem.
- **[J]** Server CPU is at 100%. `top` shows nothing using more than 10%. What's going on?
- **[M]** Disk is full. `df` says 100%, `du` says 60%. Explain.
- **[M]** Your service can `connect()` to a remote port locally but not from a colleague's box on the same network. Debug.
- **[S]** Design a baseline Linux hardening + observability layer for 10000 EC2 instances. What's on every box, what isn't, why.
- **[S]** A latency-sensitive service has unexplained 50ms tail spikes. CPU and memory look fine. Walk through how you'd profile this without a debugger.

## Monitoring & observability

- **[J]** What's the difference between a metric, a log, and a trace? Pick one and tell me when you'd reach for it first.
- **[J]** Your alert is firing constantly and the team is muting it. What do you do?
- **[M]** Design SLOs for a checkout API. Three SLIs minimum.
- **[M]** Your Prometheus is OOMing. Cardinality is up. Walk through the diagnosis and the fix.
- **[S]** Pick between Datadog, self-hosted Prometheus + Grafana + Loki + Tempo, and a Honeycomb-style vendor for a 200-engineer Series-C startup. Defend.
- **[S]** Design an on-call rotation + alert routing for a 12-engineer team that owns 40 services. Anti-burnout, low-noise.
- **[ST]** Your org spends $2M/year on observability vendor. CTO wants it cut by 40% without hurting MTTR. Plan.

## System design

- **[M]** Design a URL shortener for 100M DAU. Walk through data model, write path, read path, cache.
- **[M]** Design rate limiting for a public API. 1M req/s peak. Per-user, per-IP, per-API-key.
- **[S]** Design a multi-region active-active session store with strong-ish consistency for login.
- **[S]** Design CI/CD for a monorepo of 1000 services such that a 1-line change doesn't trigger a 4-hour build.
- **[S]** Design a feature flag service for a company with 800 engineers. SDK, evaluation latency, audit log, kill switch.
- **[ST]** Design the next-gen platform for a company that is currently on EC2 + Chef + Capistrano. Migration path, team structure, 18-month roadmap.
- **[ST]** Walk me through how you'd design Kubernetes from scratch if Kubernetes didn't exist. What primitives, what tradeoffs would you make differently?

## Networking

- **[J]** Two pods in the same namespace can't talk. Walk through the debug.
- **[J]** What's the difference between a NodePort, a ClusterIP, and a LoadBalancer service? When would you reach for each?
- **[M]** A pod can reach a service in another namespace but the same service can't reach back. NetworkPolicy is set. Find it.
- **[M]** TLS handshake is failing intermittently between two services in the same VPC. Debug.
- **[S]** Design private connectivity between two AWS accounts owned by different teams without using the public internet. Cost-conscious.
- **[S]** A latency-sensitive service runs in eu-west-1 but its primary database is in us-east-1. Defend or change the design.

## Security

- **[J]** A teammate committed an AWS access key to a public repo. Walk through your response in the next 10 minutes.
- **[M]** You inherit a K8s cluster with no NetworkPolicies, no Pod Security, no audit logging. Pick two things to ship this week and explain why those.
- **[M]** Design secret rotation for a 30-service estate using AWS Secrets Manager. RTO under 5 minutes per secret.
- **[S]** Argue for or against running an in-cluster service mesh for a 50-service estate. Then argue the other side.
- **[S]** Pen-test report says your CI runners can read prod secrets via OIDC misconfiguration. Walk me through the fix and how you'd prevent it from regressing.
- **[ST]** Design a least-privilege model for a 500-engineer org migrating from AWS IAM users to SSO + role-based access. Six-month plan.

---

## Generation guidance

When generating fresh questions:
- Stay in the patterns from `references/question-patterns.md` (incident / design / migration / tradeoff / postmortem).
- Tune the scale numbers and tech stack to the candidate's context if they shared any (e.g., "you said you're at a fintech — let's say this is a payments API").
- Don't repeat seeds the candidate has already seen (ask if they've done a mock with you before, and avoid reusing those exact questions).
- For Mixed mode, pick across topics roughly proportional to what the tier emphasizes — e.g., MANG mixes always include 1 system-design and 1 behavioral.
