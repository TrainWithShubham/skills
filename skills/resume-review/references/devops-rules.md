# DevOps / SRE / Cloud / Platform Resume Rules

This reference captures the rules that matter most for resumes targeting DevOps, SRE, Cloud, Platform, or Infrastructure engineering roles. The principles below come from real hiring patterns — use them when analyzing any DevOps-adjacent resume.

---

## The 7 Deadly Sins (detailed)

These are the most common reasons DevOps resumes get auto-rejected. Check each one explicitly.

### Sin 1: Tool Vomit

**What it looks like:**
> Skills: Docker, Kubernetes, Jenkins, AWS, GCP, Azure, Terraform, Ansible, Puppet, Chef, Prometheus, Grafana, ELK, Datadog, Python, Bash, Go, Java, Git, GitHub, GitLab, ArgoCD, Helm, Istio, Nginx, HAProxy...

**Why it fails:** A recruiter scanning this in 6 seconds learns nothing about what the candidate can actually do. A hiring manager reading it assumes the candidate has shallow exposure to all of them. ATS systems do match keywords, but without categorization the resume reads as spam.

**Fix:** Use the tiered/categorized approach:
```
Containers & Orchestration: Docker, Kubernetes, Helm, ArgoCD
CI/CD: Jenkins, GitHub Actions, GitLab CI
Cloud: AWS (EC2, EKS, Lambda, S3, IAM), GCP basics
IaC: Terraform, Ansible
Monitoring: Prometheus, Grafana, ELK Stack
Scripting: Python, Bash, YAML
```

### Sin 2: Zero Metrics

**What it looks like:**
> Managed CI/CD pipelines for the team.

**Why it fails:** "Managed" could mean anything from "wrote the Jenkinsfile" to "oversaw a 50-pipeline fleet." Without a number, the impact is invisible. Hiring managers default to the low end.

**Fix:** Add scale and outcome.
> Managed 40+ CI/CD pipelines across 6 services, enabling 15 deployments/day up from 3/week.

### Sin 3: "Responsible for..."

**What it looks like:**
> Responsible for monitoring production systems.

**Why it fails:** Passive voice hides agency. It describes a role assignment, not what the candidate did. It also signals the candidate doesn't know to lead with action verbs.

**Fix:** Start with a power verb, describe the action, quantify.
> Built observability stack (Prometheus + Grafana + PagerDuty) across 50+ services, reducing MTTR from 3 hours to 25 minutes.

**Power verbs for DevOps:** Automated, Migrated, Reduced, Architected, Implemented, Optimized, Containerized, Orchestrated, Monitored, Scaled, Deployed, Built, Shipped, Cut, Eliminated, Consolidated.

### Sin 4: Generic Summary

**What it looks like:**
> Passionate DevOps engineer seeking opportunities to grow in a dynamic environment and contribute to the organization's success.

**Why it fails:** Zero information density. Every generic word ("passionate", "dynamic", "grow", "contribute") could be replaced with a concrete fact and the resume would be stronger.

**Fix — the formula:** `[Role] with [X years] experience in [top 3 domains]. [Biggest achievement with number]. [Key differentiator].`

**Fresher example:**
> DevOps enthusiast with hands-on experience in CI/CD, Docker, and AWS through 3 personal projects and a 6-month internship. Built an automated deployment pipeline that reduced release time from 2 hours to 15 minutes. AWS Cloud Practitioner certified.

**Experienced example:**
> Senior DevOps Engineer with 5+ years building scalable infrastructure on AWS and GCP. Led migration of 30+ microservices to Kubernetes, cutting deployment failures by 80% and infra costs by 35%. Passionate about platform engineering and developer experience.

### Sin 5: Multi-page Bloat

**Rules:**
- Freshers (0-1 year): **1 page.** No exceptions.
- Mid-level (2-5 years): 1-2 pages (prefer 1 if possible, 2 if you have real content).
- Senior / Lead (5+ years): **max 2 pages.** Most recent role gets the most space.

**Why it fails:** Recruiters spend 6 seconds on the first scan. A 4-page resume signals that the candidate can't prioritize — and they never read past page 2 anyway.

### Sin 6: No Projects Section

For freshers, the projects section IS their experience — personal projects, hackathons, college work are what show initiative and learning. A fresher without a projects section has nothing to offer besides coursework.

For experienced candidates, projects differentiate you from everyone else with the same job titles. "I managed Kubernetes" is generic; "I led the zero-downtime migration from ECS to EKS for 30M daily API requests" is a story.

**Project template:**
```
Project Name | Tech Stack | Duration
- What you built + why
- Key technical decisions you made
- Quantifiable result or outcome
```

### Sin 7: Ignoring Keywords

ATS systems match keywords **literally**. "K8s" and "Kubernetes" are not the same token. "GHA" and "GitHub Actions" are not the same token. If the JD says "Kubernetes" and the resume only says "K8s", the ATS score drops.

**Fix:** Include both the full name and the common abbreviation, especially in the skills section.
> Cloud: Amazon Web Services (AWS), Google Cloud Platform (GCP), Kubernetes (K8s)

---

## The STAR Formula for DevOps Bullets

Every experience bullet should follow: **"Did [X] using [Y], resulting in [Z] — for [S]."**

- **X** = the action (power verb + what you did)
- **Y** = the technology or tools used
- **Z** = the measurable outcome (number, percentage, scale, time)
- **S** = the specific context (optional but elevates the bullet): the business scale, the team unblocked, the initiative enabled — anything that shows why this mattered beyond the number

**Example:** "Migrated 12 microservices to EKS (X=Migrated, Y=EKS), reducing infra costs by 40% and pod startup from 90s → 12s (Z), unblocking 3 dev teams and enabling the Q2 deployment-automation initiative (S)."

Not every bullet needs the +S, but 1-2 top bullets per role should include it. It's what turns "this person hit metrics" into "this person moved the business."

**Writing rules:**
- Start with a power verb. Never "Responsible for...", never "I/We/He/She" pronouns, never passive voice.
- 3-5 bullets per role. More than 6 is bloat. The most recent role gets the most bullets.
- Every major bullet should have a number or scale signal. If you genuinely don't have one, estimate a range ("~30% cost reduction") — but some quantifier is non-negotiable.

### Metrics that matter in DevOps resumes

| Metric type | Examples |
|-------------|----------|
| Deployment frequency | weekly → 10x/day |
| Downtime / uptime | 99.9% → 99.99% uptime |
| Cost savings | Reduced AWS bill by 35% |
| MTTR improvement | 4 hours → 20 minutes |
| Build time | 45 min → 8 min with caching |
| Scale | 30M API requests/day, 1M users, 500+ services |
| Team impact | Unblocked 8 dev teams, removed 20 hrs/week toil |

If a candidate genuinely doesn't remember exact numbers, estimates framed as ranges are fine ("reduced cost by ~30%"). But some quantifier is non-negotiable.

---

## Before → After examples (from the masterclass)

| ✗ Before | ✓ After |
|----------|---------|
| Responsible for managing CI/CD pipelines | Automated CI/CD pipelines using Jenkins + ArgoCD, enabling 15 daily deployments (up from 2/week) with zero-downtime releases |
| Worked on Kubernetes clusters | Migrated 12 microservices to EKS, reducing infra costs by 40% and improving pod startup time from 90s to 12s |
| Monitored production systems | Built observability stack (Prometheus + Grafana + PagerDuty) across 50+ services, reducing MTTR from 3 hours to 25 minutes |
| Used Terraform for infrastructure | Wrote 200+ Terraform modules managing multi-account AWS infra (VPC, EKS, RDS), enabling self-service provisioning for 8 dev teams |
| Automated tasks using Python scripts | Developed Python-based auto-remediation system that detects and fixes 15+ common production incidents without human intervention, saving 20 hrs/week |
| Handled Docker containers | Containerized 20+ Java and Node.js services, standardized multi-stage Dockerfiles cutting image sizes by 60%, and enforced security scanning in CI |

---

## Section anatomy for DevOps resumes

### Ideal weighting

**Fresher:** Header 5% · Summary 10% · Skills 10% · Projects 30% · Experience/Internships 20% · Education 25%

**Experienced:** Header 5% · Summary 10% · Skills 10% · Experience 40% · Projects 20% · Education 15%

### Projects section — what recruiters look for

**Fresher project ideas that land interviews:**
- CI/CD pipeline for a personal app (GitHub Actions)
- Dockerized multi-tier app with docker-compose
- Terraform-provisioned AWS infra (VPC + EC2)
- Monitoring stack on a homelab (Prometheus/Grafana)
- GitOps deployment with ArgoCD on Minikube

**Experienced — how to frame project work:**
- Zero-downtime K8s migration (production scale)
- Self-healing infrastructure with auto-remediation
- Multi-region DR setup with RTO < 15 min
- Platform engineering: internal developer portal
- Cost optimization initiative (saved $X/month)

---

## Certifications that move the needle

| Impact tier | Certifications |
|-------------|----------------|
| High impact | CKA / CKAD, AWS Solutions Architect, Terraform Associate, RHCSA |
| Good to have | AWS Cloud Practitioner, Docker Certified, GCP Associate, Azure Fundamentals |
| Low impact | Random Udemy certificates, course completion badges, 10+ beginner certs |

**Guidance:**
- Freshers: list all relevant certs, education near the top
- Experienced: list only high-impact certs, push education to the bottom
- Include only legitimate certs — "listening to a YouTube course" is not a certification

---

## The GitHub + Blog + Resume triangle

For DevOps/engineering resumes, credibility comes from three sources:
- **Resume** says you know Terraform
- **GitHub** proves it (with repos, READMEs, commits)
- **Blog / content** explains your thinking (how you decided, what you learned)

If a DevOps candidate has no GitHub link, that's a significant gap. For senior candidates especially, active GitHub activity and clean READMEs weigh more than star count.
