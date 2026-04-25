# Keywords & Semantic Entity Bank

Use this when scoring **Discoverability & Keywords (25 pts)** and when building the Headline / About / Skills rewrites. LinkedIn's LLM-based ranking systems (360Brew, JUDE, Post Embeddings — see `sources.md`) read the profile as a holistic entity, so isolated keywords without their semantic neighbors read as shallow.

## How to use this file

1. **Identify the candidate's primary cluster** from the JD and current profile (e.g., "Kubernetes Platform Engineer" → Cluster: K8s/Platform).
2. **Check coverage of the cluster's core terms AND its semantic neighbors.** A profile listing `Kubernetes` without `Helm`, `Argo CD`, `kubectl`, `kubelet`, `etcd`, or `cluster autoscaler` reads thin.
3. **Score Top 3 skills carefully.** Order matters — the first skill carries the most weight. Top 3 should match the *role being targeted*, not the role currently held.
4. **Flag credential-anchor candidates.** LinkedIn discontinued Skill Assessments and purged their badges in 2024. The replacement mechanic — Verified Skills — anchors a skill to a verified workplace, education, or **synced certification** under Licenses & Certifications. Skills marked **★** below have widely-available, LinkedIn-syncable certifications that serve as the modern credibility signal. Recommend the user pursue these as time/budget allow.

Skills cap is **100** (LinkedIn doubled it from 50 in early 2024). Don't max out blindly — quality beats quantity. Target 15–30 highly relevant skills with ≥1 endorsement each (skills with 0 endorsements don't factor into search) and reserve the Top 3 for the most marketable, JD-aligned terms.

---

## DevOps / SRE / Platform / Cloud — primary depth

### Cluster A: Cloud Platforms

**AWS (most common, deepest neighbor list)**
- Core: AWS ★, EC2, S3, VPC, IAM, Route53, CloudFront, RDS, Lambda
- Compute/Containers: ECS, EKS, Fargate, App Runner
- Networking: VPC peering, Transit Gateway, PrivateLink, Direct Connect, NAT Gateway
- Observability: CloudWatch, X-Ray, CloudTrail
- Security: KMS, Secrets Manager, GuardDuty, Security Hub, WAF
- Data: DynamoDB, Aurora, Redshift, Athena, Glue, Kinesis
- Cost/Governance: AWS Organizations, Service Control Policies, Cost Explorer, Trusted Advisor
- Certs as keywords: AWS Solutions Architect, AWS DevOps Engineer Professional, AWS SysOps

**Azure**
- Core: Azure ★, Azure AD / Entra ID, Resource Manager (ARM), Bicep
- Compute: AKS, App Service, Azure Functions, VM Scale Sets
- Data: Cosmos DB, Azure SQL, Synapse, Data Factory, Event Hubs
- Observability: Azure Monitor, Application Insights, Log Analytics
- Certs: AZ-104, AZ-204, AZ-305, AZ-400 (DevOps Engineer Expert)

**GCP**
- Core: GCP ★, GKE, Cloud Run, Cloud Functions, BigQuery, Pub/Sub
- Networking: VPC, Cloud Load Balancing, Cloud Armor, Cloud CDN
- Data: Spanner, Firestore, Dataflow, Dataproc
- Certs: Professional Cloud Architect, Professional DevOps Engineer

**Multi-cloud / cloud-agnostic**: Terraform, Pulumi, Crossplane, Cluster API, OpenTofu

### Cluster B: Containers & Kubernetes

- Core: Kubernetes ★, Docker ★, containerd, CRI-O, Helm ★, kubectl, kustomize
- Cluster components: kube-apiserver, kubelet, etcd, kube-proxy, CoreDNS, CNI
- Add-ons: Istio, Linkerd, Cilium, Calico, Flannel, MetalLB
- GitOps: Argo CD, Flux, Argo Workflows, Argo Rollouts
- Operators: Operator SDK, OLM, custom controllers, CRDs
- Storage: CSI drivers, Rook, Longhorn, OpenEBS
- Autoscaling: HPA, VPA, KEDA, Karpenter, Cluster Autoscaler
- Security: OPA, Gatekeeper, Kyverno, Falco, Pod Security Standards, Network Policies
- Certs: CKA ★, CKAD ★, CKS ★, KCNA

### Cluster C: Infrastructure as Code & Configuration

- Core: Terraform ★, Pulumi, OpenTofu, AWS CDK, Bicep, CloudFormation
- Config mgmt: Ansible ★, Chef, Puppet, SaltStack
- Modules/registries: Terragrunt, Atlantis, Spacelift, Terraform Cloud
- Testing: Terratest, Checkov, tflint, OPA/conftest, kitchen-terraform

### Cluster D: CI/CD & Build

- Core: Jenkins ★, GitHub Actions ★, GitLab CI, CircleCI, Argo Workflows, Tekton
- Build tools: Maven, Gradle, Make, Bazel, Buck, Nx
- Image building: Docker, Buildkit, Kaniko, Buildah, ko, Jib
- Artifact mgmt: Artifactory, Nexus, Harbor, ECR/GCR/ACR
- Deployment patterns: Blue/green, canary, feature flags, rollbacks, progressive delivery
- Tools: LaunchDarkly, Flagger, Argo Rollouts

### Cluster E: Observability

- Metrics: Prometheus ★, Grafana ★, VictoriaMetrics, Mimir, Cortex, Thanos
- Logging: ELK / Elastic Stack ★, Loki, Fluentd, Fluent Bit, Vector, Splunk
- Tracing: Jaeger, Zipkin, Tempo, OpenTelemetry ★
- APM/SaaS: Datadog ★, New Relic, Dynatrace, Honeycomb, Lightstep, Sentry
- Concepts: SLI, SLO, SLA, error budgets, RED method, USE method, golden signals
- Incident response: PagerDuty, Opsgenie, Incident Commander, postmortems, blameless culture

### Cluster F: SRE & Reliability

- Core: SRE, Reliability Engineering, MTTR, MTBF, MTTD, MTTA
- Practices: chaos engineering, game days, runbooks, toil reduction, capacity planning
- Tools: Chaos Mesh, Litmus, Gremlin, AWS Fault Injection
- Patterns: circuit breakers, bulkheads, retries with exponential backoff, idempotency
- Concepts: error budget policy, burn rate alerts, SLO-based alerting, blameless postmortems

### Cluster G: Security / DevSecOps

- Core: DevSecOps, Application Security, Cloud Security, Zero Trust
- SAST/DAST/SCA: Snyk, Checkov, Trivy, Grype, Semgrep, SonarQube, OWASP ZAP
- Secrets: HashiCorp Vault ★, AWS Secrets Manager, Sealed Secrets, External Secrets Operator
- Supply chain: SBOM, SLSA, Sigstore, Cosign, in-toto, dependency pinning
- Compliance: SOC 2, ISO 27001, HIPAA, PCI-DSS, FedRAMP, CIS benchmarks
- Identity: OIDC, SAML, OAuth 2.0, RBAC, ABAC, IAM
- Certs: CKS, CCSP, AWS Security Specialty, Security+

### Cluster H: Networking

- Core: TCP/IP, BGP, DNS, HTTP/HTTPS, TLS, mTLS, gRPC
- Service mesh: Istio, Linkerd, Consul Connect, AWS App Mesh
- Load balancing: NGINX, HAProxy, Envoy, ALB/NLB, Traefik
- Edge: CloudFlare, Fastly, Akamai
- API gateways: Kong, Apigee, AWS API Gateway, Tyk

### Cluster I: Databases & Data Platform

- Relational: PostgreSQL ★, MySQL ★, Oracle, SQL Server
- NoSQL: MongoDB ★, Cassandra, DynamoDB, Redis ★, Memcached
- Search: Elasticsearch, OpenSearch, Solr
- Streaming: Kafka ★, Pulsar, Kinesis, RabbitMQ ★, NATS
- Warehouses: Snowflake, BigQuery, Redshift, Databricks
- Concepts: replication, sharding, partitioning, CDC, schema migrations, query optimization

### Cluster J: Programming languages (for DevOps/SRE)

- **Most relevant:** Python ★, Go ★, Bash/Shell ★, YAML, HCL
- Secondary: TypeScript/JavaScript (CDK, Pulumi), Rust (newer infra tools), Groovy (Jenkins)

---

## Adjacent technical clusters — shorter coverage

### Backend / Software Engineer

- Languages: Java ★, Python ★, Go ★, TypeScript/JavaScript ★, C# ★, Rust, Kotlin
- Frameworks: Spring Boot ★, Django ★, FastAPI, Express, NestJS, .NET, Gin, Echo
- API: REST, GraphQL, gRPC, OpenAPI/Swagger, Webhooks
- Patterns: microservices, event-driven, CQRS, hexagonal architecture, DDD, SOLID
- Testing: JUnit, pytest ★, Jest, Mocha, integration testing, contract testing

### Frontend / Full-stack

- Frameworks: React ★, Next.js, Vue, Svelte, Angular ★
- Languages: TypeScript ★, JavaScript ★, HTML, CSS
- Styling/UI: Tailwind, Material UI, shadcn/ui, Chakra
- State: Redux, Zustand, React Query, TanStack
- Tooling: Vite, Webpack, esbuild, Turbopack
- Testing: Jest ★, Vitest, Playwright, Cypress, Testing Library

### Data Engineering

- Orchestration: Airflow ★, Dagster, Prefect, Argo Workflows
- Processing: Spark ★, Flink, Beam, dbt ★
- Storage/Lake: Iceberg, Delta Lake, Hudi, Parquet
- Streaming: Kafka, Kinesis, Flink, Spark Streaming
- Warehouses: Snowflake ★, BigQuery, Redshift, Databricks

### ML / AI Engineering

- Frameworks: PyTorch ★, TensorFlow ★, JAX, scikit-learn ★
- LLMs/GenAI: LangChain, LlamaIndex, vLLM, Hugging Face, RAG, vector databases (Pinecone, Weaviate, pgvector, Qdrant)
- MLOps: MLflow, Kubeflow, SageMaker, Vertex AI, Weights & Biases, BentoML
- Serving: Triton, TorchServe, KServe, Ray Serve

### Mobile

- iOS: Swift ★, SwiftUI, UIKit, Xcode, Combine
- Android: Kotlin ★, Jetpack Compose, Android Studio, Coroutines
- Cross-platform: React Native ★, Flutter ★, Expo

### Security Engineer (deeper than DevSecOps)

- Offensive: penetration testing, red team, OSCP ★, OSEP, Burp Suite, Metasploit
- Blue team: SIEM (Splunk, Sentinel, Chronicle), SOAR, threat hunting, MITRE ATT&CK
- AppSec: secure code review, threat modeling (STRIDE, PASTA), OWASP Top 10
- Cloud security: CSPM (Wiz, Prisma Cloud, Lacework), CNAPP, CIEM

---

## Headline keyword strategy by level

### Fresher (0-1 yr)
Lead with the **target role**, not "Aspiring" or "Looking for opportunities" — those phrases dilute searches.
- ✗ "Aspiring DevOps Engineer | Open to Work | Recent CS Graduate"
- ✓ "DevOps Engineer | AWS · Kubernetes · Terraform | CKA Certified | Built CI/CD pipeline reducing deploy time 60%"

### Mid-level (2-5 yr)
Lead with role + 3 specialty technologies + one signature outcome.
- ✓ "SRE @ [Company] | Kubernetes · Prometheus · Go | Cut p99 latency 40% across 30 microservices"

### Senior (5+ yr)
Lead with role + scope/scale + leadership signal.
- ✓ "Staff Platform Engineer | Multi-cluster K8s @ scale (1000+ nodes) | Built internal developer platform serving 200+ engineers"

---

## Top 3 Skills — alignment patterns

The first skill is the most heavily weighted in search. Order them like a sentence: **what you are → what you specialize in → your edge.**

| Target role | Recommended Top 3 (in order) |
|-------------|------------------------------|
| DevOps Engineer | Kubernetes → AWS (or Azure/GCP) → Terraform |
| SRE | Kubernetes → Prometheus → Go (or Python) |
| Platform Engineer | Kubernetes → Terraform → Argo CD (or Backstage) |
| Cloud Architect | AWS (or Azure/GCP) → Terraform → Kubernetes |
| DevSecOps | Kubernetes → AWS Security → HashiCorp Vault |
| Backend Engineer | [Primary language] → [Primary framework] → AWS (or relevant cloud) |
| Data Engineer | Apache Spark → Airflow → SQL (or Snowflake) |
| ML Engineer | PyTorch (or TensorFlow) → MLOps → Python |

If the candidate's current Top 3 don't match this pattern for their target role, **flag it as a discoverability fix.** This is one of the highest-leverage 5-minute changes.

---

## Semantic-entity coverage scoring shortcut

For the Discoverability dimension, when assessing the candidate's Skills + About + Experience together:

- **Strong (20-25 pts):** primary cluster fully covered, 5+ semantic neighbors, Top 3 aligned with target role, 3+ verified badges.
- **Solid (15-19 pts):** primary cluster mostly covered, 2-3 neighbors, Top 3 close but not perfect, 1-2 verified badges.
- **Thin (10-14 pts):** core terms only, no semantic neighbors, Top 3 reflects current role not target, no verified badges.
- **Weak (<10 pts):** missing core cluster terms, generic skills, Top 3 unrelated to target role.

A profile that lists "Kubernetes, Docker, AWS" and stops there is **thin**, not strong, by 2026 standards. Strong = "Kubernetes, Helm, Argo CD, Cluster Autoscaler, kubectl, OPA Gatekeeper, AWS EKS, Terraform" — the entity-mapping engine reads that as a coherent platform engineer.

---

## Credential anchors — what to pursue (replaces dead Skill Assessments)

LinkedIn discontinued Skill Assessments and purged the badges in 2024. The modern mechanic is **Verified Skills**: anchor a skill to a credential. The credentials below are widely available, recognizable to recruiters, and sync cleanly into LinkedIn's Licenses & Certifications section. Once added there, tag the related skill to the credential — that's how a skill becomes "verified" in the 2024–2026 model.

**Tier 1 (highest signal, prioritize):**
- AWS Solutions Architect Associate / Professional · AWS DevOps Engineer Professional
- CKA (Certified Kubernetes Administrator) · CKAD · CKS
- HashiCorp Certified: Terraform Associate
- Microsoft Certified: Azure Administrator (AZ-104) / Azure DevOps Engineer Expert (AZ-400)
- Google Professional Cloud Architect / Professional DevOps Engineer

**Tier 2:**
- Docker Certified Associate
- Red Hat Certified Engineer (RHCE)
- Linux Foundation Certified Engineer (LFCE)
- Prometheus Certified Associate (PCA)
- Istio Certified Associate (ICA)
- Argo Project Associate

**Tier 3 (broader / specialty):**
- AWS Security / Networking / Database Specialty
- KCNA, KCSA, GitOps Certified Associate
- HashiCorp Vault Associate, Consul Associate
- Postgres Certified Associate

Other strong credibility signals that aren't certifications:
- **Microsoft Entra Verified Workplace** (the Verified-on-LinkedIn mechanic — see SKILL.md). One-time, free, ~60% more profile views per LinkedIn first-party data.
- **Synced Microsoft Learn / AWS Skill Builder badges** — automatically pull into Licenses & Certifications.
- **Recommendations from senior engineers at credible companies** (5–10 is the sweet spot).

3+ tagged credentials + Verified Workplace ≈ a noticeable edge over uncredentialed peers in recruiter search and trust signaling.
