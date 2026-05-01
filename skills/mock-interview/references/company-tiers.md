# Company tiers — what each one signals on

The same job title means different things at different tiers. Calibrate the question style, follow-ups, and bar to the tier the candidate is targeting.

## Service company

**Examples:** TCS, Infosys, Wipro, Capgemini, Accenture, HCL, LTIMindtree, Cognizant, Tech Mahindra.

**Interview shape:**
- Heavier on tooling breadth, lighter on first-principles depth.
- Tickets, change management, ITIL, ServiceNow, on-call rotation flow.
- Jenkins on VMs is still a real answer. So is Ansible. So is "we maintain a Confluence runbook."
- Cloud questions are usually AWS or Azure (not GCP) and lean toward managed services + cost reporting, not bleeding-edge primitives.
- Behavioral weight: client-facing maturity, working across timezones, escalation paths.

**Bar:**
- Junior: knows the tool stack, can follow a runbook, asks clarifying questions before acting.
- Mid: owns a service, writes runbooks, handles a P2 without paging the lead.
- Senior: leads a small team, talks to client architects, makes "build vs buy" calls within a known stack.
- Staff+: rare role here; usually reframed as "Architect" — owns multi-account / multi-region setup for a client.

**Common gotchas to probe:**
- Do they actually understand *why* a tool works, or only how to operate it?
- Can they name one alternative to their daily tool and a tradeoff between them?
- Have they ever tuned anything beyond defaults?

## Product company

**Examples:** Razorpay, Zerodha, Swiggy, Zomato, PhonePe, CRED, Atlassian, GitHub-style mid-cap, Postman, Hasura, Browserstack, mid-stage YC startups.

**Interview shape:**
- Depth on **one** stack the company actually runs (often AWS-heavy or GCP-heavy, K8s on top).
- Real scale problems: rate limiting, multi-region, eventual consistency, hot keys, cost-per-request.
- Reliability culture: SLOs, error budgets, blameless postmortems, runbooks-as-code.
- Cost matters: candidates who can't reason about $/request lose points.
- Often a system-design round. Often a debug-the-broken-system round.

**Bar:**
- Junior: junior-mid hybrid; expected to own a small service end-to-end inside 3 months.
- Mid: independent on day-to-day, designs simple systems, knows one tradeoff per primitive (e.g., why pick SQS over Kafka here, why pick RDS over DynamoDB there).
- Senior: owns a domain (e.g., payments infra, search infra). Decides platform direction. Mentors. Carries pager and writes the postmortem.
- Staff+: cross-team architecture, sets standards (e.g., "this is how we do K8s here"), picks battles, drives multi-quarter initiatives.

**Common gotchas to probe:**
- "How would this fail?" — strong candidates volunteer failure modes; weak ones wait to be asked.
- "What does this cost at 10x traffic?" — handwaves are a -1.
- "Walk me through the last incident you actually owned" — STAR format with metrics or it didn't happen.

## MANG / FAANG

**Examples:** Meta, Apple, Netflix, Google, Amazon, Microsoft. Add: Stripe, Databricks, Snowflake, Cloudflare, OpenAI, Anthropic — same bar.

**Interview shape:**
- Systems thinking over tooling. They don't care if you've used their internal stack — they care if you reason well from primitives.
- Ambiguity tolerance: scenarios are deliberately under-specified; the candidate has to ask the right clarifying questions before designing.
- Coding round is normal even for SRE/DevOps/Platform — Python/Go, leetcode-easy-to-medium, or scripting-heavy.
- Behavioral round (Amazon's LP loop, Google's "Googleyness", Meta's "execution") is a real round, not a checkbox. Specific examples with metrics, structured.
- Long-loop: 4-6 rounds. Bar-raiser at Amazon, hiring committee at Google.

**Bar:**
- Junior: rare — usually L3/E3/SDE-1 hire from new-grad pipeline, not from market.
- Mid (L4/E4/SDE-2): designs a service, on-call lead, pushes back on bad designs.
- Senior (L5/E5/SDE-3): owns reliability of a product surface, mentors L4s, makes platform calls that cost real money to reverse.
- Staff (L6/E6): cross-org influence, sets technical strategy, identifies and unblocks org-wide problems.
- Principal (L7+): industry-visible, defines roadmaps that span years.

**Common gotchas to probe:**
- "What's the simplest thing that would work?" — over-engineering is a real signal at this tier.
- "What metric would you watch to know this is working?" — strong candidates name the metric, the threshold, and the alert condition.
- "What's the failure mode you're most worried about?" — strong candidates have one; weak ones say "we have monitoring."
- For Amazon: every behavioral answer must map cleanly to one or two Leadership Principles. "Customer Obsession", "Ownership", "Bias for Action", "Dive Deep", "Earn Trust", etc.
- For Google: scale and elegance. "How does this work at a billion users?" is a real follow-up, not a flex.
- For Meta: "what would you ship this week?" — execution speed signal.

## Tier-mapping cheat sheet

| Dimension | Service | Product | MANG/FAANG |
|---|---|---|---|
| Question style | Tooling-heavy | Scenario-heavy | Open-ended ambiguity |
| Depth expected | Working knowledge | Domain depth | First-principles + scale |
| Cost reasoning | Light | Required | Required, with numbers |
| Coding round | Rare | Sometimes | Always |
| System design | Sometimes | Always | Always, multiple |
| Behavioral weight | Client-facing | Postmortem-style | Loaded — full round |
| Acceptable answer to "I don't know" | Honest fallback to docs | Reason from primitives | Reason from primitives, then propose how you'd find out |

## Calibration rule

If unsure where the bar lands, default **down** half a notch from the candidate's stated tier. A candidate who passes a slightly-too-hard mock is more prepared than one who passes a too-easy one.
