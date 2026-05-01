# Question patterns — how to shape a scenario question

Scenario questions test how the candidate thinks. Trivia questions test what they memorized. Always reach for the former.

## The five patterns

Every question in the seed banks (and every fresh question you generate) should fit one of these. If a candidate-facing question doesn't fit, it's probably trivia.

### 1. Incident / debug

> "Your <thing> is <broken state>. Walk me through your debugging."

The candidate has to enumerate hypotheses, prioritize, name the commands/dashboards they'd actually use, and know when to escalate.

**Examples:**
- "Pods in your production namespace are stuck in `CrashLoopBackOff` after a deploy that worked in staging. Walk through your debug."
- "EC2 instances behind your ALB are all marked unhealthy at 3am. Health checks were green 5 minutes ago. What do you do?"
- "Terraform plan shows a destroy on the prod RDS. You didn't change the RDS resource. What's going on, and what do you do *before* you run apply?"

**Strong-candidate behavior:** asks clarifying questions, names specific commands and what they expect each to show, picks the most likely cause first based on recent changes, has a "stop and roll back" trigger.

### 2. Design

> "Design <system> for <scale or constraint>."

The candidate has to ask clarifying questions, decompose, name primitives, and reason about tradeoffs.

**Examples:**
- "Design a multi-region active-active CI/CD system that supports 5000 engineers and 50000 builds/day. Cost-conscious."
- "Design log aggregation for a fleet of 10000 EC2 instances across 3 regions. Budget is $50k/month."
- "Design the rollout strategy for a new K8s cluster upgrade across 200 production clusters."

**Strong-candidate behavior:** clarifies before designing, lays out 2-3 candidate architectures and rejects all but one, talks about failure modes, talks about cost, talks about how they'd verify it's working.

### 3. Migration

> "Migrate from <state A> to <state B> without downtime."

Tests practical experience with state, traffic, rollback, and the boring infra reality.

**Examples:**
- "Migrate a self-managed Postgres on EC2 to RDS Aurora with zero downtime. The DB is 4TB, 30k QPS."
- "Migrate from Jenkins on VMs to GitHub Actions, 200 pipelines, 30 engineers, no week-long freeze."
- "Migrate stateful workloads from Docker Swarm to Kubernetes across 3 environments."

**Strong-candidate behavior:** picks a migration pattern (dual-write, shadow-traffic, blue-green, expand-contract) and explains why; has a rollback plan that doesn't lose data; has a verification step.

### 4. Tradeoff / decision

> "Pick between A and B for <constraint>. Defend your choice."

Tests opinions and the reasoning behind them.

**Examples:**
- "EKS or self-managed K8s on EC2 for a 50-person fintech startup. Defend your choice."
- "Push-based (CI/CD) or pull-based (GitOps) deployment for a 200-cluster K8s estate. Why?"
- "CloudWatch Logs or self-hosted Loki for a $2M/year cloud spend. What do you pick and what do you regret?"

**Strong-candidate behavior:** picks one and *names what they're giving up*; quantifies where they can; references real experience or specific data.

### 5. Postmortem / behavioral

> "Tell me about a time you <hard thing>." or "Walk me through your last <incident / decision / migration>."

Tests whether they actually own things, what they learned, what their decision-making feels like in the wild.

**Examples:**
- "Walk me through the most recent production incident you owned. What was the impact, what did you do, what did the postmortem say, what changed?"
- "Tell me about a technical decision you made that you later reversed. What did you miss?"
- "Tell me about a time you pushed back on a senior engineer or manager. How'd you handle it?"

**Strong-candidate behavior:** STAR format with metrics; takes ownership rather than blames; names the lesson learned and what they did differently next time.

## Anti-patterns — questions to avoid

These show up in interview prep books and on social media but produce zero signal:

- ❌ "What's the difference between Deployment and StatefulSet?" → recall, not reasoning.
- ❌ "What is a load balancer?" → too broad.
- ❌ "What are the 4 pillars of observability?" → cargo trivia.
- ❌ "Explain the OSI model." → only useful if it leads somewhere ("you said TLS — at what layer?").
- ❌ "What's your favorite tool?" → no signal; everyone says "Terraform".

## Reshaping trivia into scenarios

If you find yourself reaching for trivia, reshape it:

| Trivia | Scenario |
|---|---|
| "What's a StatefulSet?" | "You have a StatefulSet stuck `Pending` after a node failure — debug it." |
| "What's a Service of type LoadBalancer?" | "Your LB Service in EKS isn't reachable from outside. What's wrong?" |
| "Explain CI/CD." | "Your CI pipeline takes 45 minutes. Where do you cut?" |
| "What is auto-scaling?" | "Your HPA is scaling pods, but request latency is still rising. Why?" |
| "What is a VPC?" | "You can't connect to RDS from your EKS pods in the same VPC. Walk through your debug." |

Same topic. The scenario version generates 10x the signal.

## Follow-up patterns

After the candidate answers, **one** follow-up. Pick the one that probes the weakest part of their answer:

- **Scale push:** "Now do that at 10x traffic."
- **Cost push:** "What does this cost per month at that scale?"
- **Failure push:** "How does this fail? Walk me through the worst-case incident."
- **Operations push:** "How would you know this is working? What metric, what threshold?"
- **Rollback push:** "If this deploy goes wrong, how do you roll back?"
- **Simplification push:** "What's the simplest version that still meets the requirement?"
- **Tradeoff push:** "What did you give up by choosing this approach?"

Don't pile on. One follow-up. The point is to find the *edge* of their understanding, not bury them.

## Time budget per question

- Q presentation: 15-30 seconds.
- Candidate primary answer: 2-4 minutes.
- Follow-up + answer: 1-2 minutes.
- Transition: instant.

Total per question: 4-7 minutes. A 5-question mock should run 25-35 minutes plus the report.
