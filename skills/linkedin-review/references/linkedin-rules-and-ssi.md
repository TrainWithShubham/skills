# LinkedIn Rules, Algorithm & SSI Playbook

This is the core reference — algorithm model, feature-by-feature rules, and SSI action plan. Read it when analyzing headlines, About sections, experience bullets, or building the 30-day plan. Every numeric claim here traces to `references/sources.md`.

---

## What the algorithm actually does (2024–2026)

LinkedIn's ranking has shifted from keyword retrieval to LLM-based semantic ranking. The deployed systems are public:

- **360Brew** — a 150B-parameter foundation model fine-tuned on LinkedIn data, used across 30+ predictive tasks (arXiv 2501.16450).
- **JUDE** — LLM-based representation learning for job recommendations (LinkedIn Engineering blog).
- **Post Embeddings** — LLM-based feed retrieval, in production 2+ years (arXiv 2405.11344, CIKM 2025).
- **AI-Powered People Search** — natural-language people search launched November 13, 2025 for US Premium members.

**Practical implication:** Listing "Kubernetes" as a skill isn't enough. The model reads your profile holistically and weights the **semantic neighbors** — EKS/GKE/AKS/Helm/Argo CD/kubectl/etcd. For each major technology you claim, make sure 2–3 related concepts appear in About, Experience, or Skills. See `references/keywords-bank.md` for clusters.

---

## Dwell time is a real signal — but soften the numbers

LinkedIn's engineering blog (May 2020, still live) confirms dwell time as a feed ranking signal. Posts where readers spend more time are pushed to wider audiences.

The widely-cited "61 seconds = 13× more reach" is a **third-party engagement-rate ratio, not a LinkedIn-published reach figure** — closer to "posts with 61+ seconds of dwell show ~13× the engagement rate of 0–3-second scrolls." When citing in a review, frame it that way.

What this means for the user: **dwell-time-driving formats win.** Carousels and substantive long-form text outperform single-sentence updates. Don't post and run — the first hour matters because LinkedIn's initial-audience push is the gatekeeper to wider reach.

---

## Comments vs likes — direction is right, multiplier is folklore

Per Van der Blom's 2025 Algorithm Insights Report (1.8M post sample, the gold standard):

- **Substantive comments (15+ words)** drive significantly more reach than likes.
- **Back-and-forth threads with 3+ participants** amplify reach roughly **5×** — the strongest documented multiplier.
- LinkedIn has not published an exact comment-to-like weighting, so don't quote "15× more weight" as fact.

What this means for action plans: a 2-sentence comment that adds to the conversation beats 50 reactions. A reply that triggers back-and-forth beats a one-shot comment.

---

## External link reach — a tension, not a certainty

In August 2025, LinkedIn's Sr. Director of Product Management publicly stated that posts with links are **not intentionally penalized**. Practitioner data still shows ~25–50% lower impressions on link-bearing posts.

What this means: don't lecture users about a "60% link penalty" — that's outdated. Frame it as: "LinkedIn says no intentional penalty; third-party data still shows reduced reach. Native articles and newsletters are link-penalty-free either way." The "link in first comment" workaround still narrowly wins (−5–10% vs −25–50%) but the gap is closing.

---

## Content format reach (Van der Blom 2025)

| Format | Notable data |
|--------|--------------|
| **Polls** | ~1.64× reach multiplier — top relative performer. 7-day duration; 3 options optimal. |
| **PDF / document carousels** | Once dominant, now declining as LinkedIn penalizes low completion rates. Best length: 8–10 slides. |
| **Native video** | Down ~72% YoY in reach per Van der Blom; still strong for personal-brand engagement. |
| **Single image** | Mid-tier; +50% lift if the image features a face. |
| **Text-only** | Lowest engagement rate, but well-formatted text (2–4 sentence paragraphs, line breaks for skim) still performs. |
| **Native articles / newsletters** | Bypass the link discussion entirely; newsletters get 40–60% email open rates and push notifications to subscribers. |

Posting frequency sweet spot: **2–5 posts per week** (Buffer's 4.8M-post study). Daily posting now correlates with reach decline if quality drops. Best window: **Tuesday–Thursday, 10–11 AM** (Sprout Social 2026).

Other current dos and don'ts:
- **Hashtags drastically reduced.** 1–3 max — not 5–10. **Creator Mode and "Talks About" were retired in early 2025.**
- **AI-detected posts get ~30% less reach and ~55% less engagement** (Originality.AI 2025). Use AI as a draft generator, then personalize heavily.
- **Engagement pods are now a real risk.** Documented shadow-bans of 60–90 days. Don't recommend them.
- **Broetry / one-line-per-paragraph theatrics are flagged as bait.** Use line breaks for scannability, not as a "see more" trick.

---

## Recruiter "Spotlights" — the real "active candidate" mechanic

There is **no documented "active in last 6 months" filter.** That's folklore. The real mechanic is LinkedIn Recruiter's Spotlight system (LinkedIn Recruiter Help, page a414283). The Spotlights are:

| Spotlight | What it surfaces |
|-----------|------------------|
| Open to Work | Members who've signaled openness |
| Active Talent | Members with recent profile updates / engagement |
| More Likely to Respond | Recently updated profile, longer-than-average tenure, or at companies with announced layoffs |
| Past Applicants | Candidates who previously applied |
| Company Followers | Followers of the recruiter's company |
| Internal Candidates | ≥6 months in current role (the only Spotlight with a published time threshold) |
| Rediscovered Candidates | Past pipeline candidates |

Spotlight-featured candidates get **64% higher InMail responses, 2× more likely to reply** (LinkedIn Talent Blog). So while there's no day-threshold filter, **recent updates and engagement keep you in those candidate pools.**

---

## InMail economics — why recruiters are picky in 2026

These numbers explain *why* a generic profile gets ignored:

- **LinkedIn-published average InMail response rate: 18–25%** (3× cold email).
- **Recruiter quota:** must hold ≥13% reply rate over 14 days on 100+ messages or risk credit refund/throttling. This forces selectivity.
- **Per-credit cost:** ~$10 in 2026; ~$900–$3,000 in credits per placement.
- **Personalized vs bulk:** 40–44% acceptance lift for personalized messages.
- **Reply timing:** 65% within 24h, 90% within a week.

Practical implication: when you tell the user their "engagement isn't moving," remind them recruiters now spend their InMail credits on Spotlight-featured, well-targeted candidates — not on the broader pool.

---

## Open to Work — the under-used recruiter-only mode

LinkedIn's first-party data: candidates with the **recruiter-only** Open-to-Work signal turned on get **14.5% positive InMail response vs 4.6% without** — roughly a 3× lift. (Source: LinkedIn Member blog.)

The public green ring is divisive — useful for early-mid career, often hurts senior. The recruiter-only mode is invisible to your current employer, has no downside for currently-employed users, and gives recruiters the strongest "available" signal.

For senior candidates without it: **switching to recruiter-only mode is one of the highest-leverage 30-second changes available.**

---

## The Headline (the heaviest-weighted ranking field)

220-character cap (unchanged). But mobile feed/search cards only render the first **~60–70 characters**, and desktop shows **~120**. Front-load identity + value. Characters 70–220 are SEO/keyword fuel that few humans read but the algorithm indexes.

### Use a named formula — don't invent one

- **Austin Belcak**: "I help [WHO] achieve [WHAT]" + variant "Your next [Role]" for the unemployed.
- **Jeff Su (two-part)**: Part 1 = keyword-stuffed identity; Part 2 = quantified value. Example: `Senior DevOps Engineer | AWS · Kubernetes · Terraform | Cut deploy times 2 hours → 12 minutes across 40 microservices`.
- **Justin Welsh**: "I help X do Y, and I'm different because Z." The differentiator is the 2025 evolution — bare "I help" templates are saturated.

### Examples by level

| Level | Headline |
|-------|----------|
| Fresher DevOps | `DevOps Engineer | AWS + Docker + Jenkins | Built 3 CI/CD pipelines, AWS Cloud Practitioner certified` |
| Mid DevOps | `DevOps Engineer | AWS + Kubernetes + Terraform | Cut infra costs 35% across 30 microservices` |
| Senior DevOps | `Senior Platform Engineer | AWS + EKS + GitOps | Led zero-downtime K8s migration for 30M req/day` |
| Career switch | `Backend → Platform Engineer | AWS + Terraform + Observability | 5 yrs Java/Spring, now building internal dev platform` |

### Headline anti-patterns
- `Software Engineer at Company X` — pure title, no value, misses keyword searches.
- `Passionate tech professional | Lifelong learner | Dreamer` — zero searchable terms.
- 10+ technologies in a row — algorithm reads as shallow without semantic neighbors.
- `DevOps Ninja 🚀🔥` — no recruiter searches for this.

---

## The About Section

2,600-character cap (unchanged). Use 1,500–2,500 for best results.

**Visible preview before "See more":** ~300 chars on desktop, **~200 chars on mobile**. The first **2 sentences should each be ≤15 words** to load fast and hook before the fold.

### 1. Hook (first ~200 chars on mobile, ~300 on desktop)

Three patterns that work (per top LinkedIn coaches):

- **Problem hook:** "Worried that one click from an employee could lead to a catastrophic data breach?"
- **Concrete result:** "Last year I led the migration that cut our AWS bill by $400K while hitting 99.99% uptime."
- **Bold claim:** "Most infra teams over-index on tooling and under-index on developer experience."

Patterns that fail:
- "Hi, I'm [Name]…" / "Thanks for visiting my profile…"
- "Results-driven DevOps professional with a passion for cloud technologies…"
- "Over X years of experience in…"

### 2. Identity paragraph (2–4 sentences after the fold)

Who you are and what you do, with target-role keywords placed naturally.

### 3. Achievement highlights (3–5 quantified wins)

> - Migrated 30+ microservices from ECS to EKS, reducing infra costs 35% and improving pod startup 90s → 12s
> - Built self-service Terraform modules adopted by 8 dev teams, cutting infra ticket queue 60%
> - Designed on-call runbook and chaos-engineering practice that reduced MTTR 4 hours → 25 minutes

### 4. Current focus / what's next

2–3 sentences signaling what you're building and what you're open to.

### 5. Skills cluster (categorized for semantic coverage)

> **Cloud:** AWS (EKS, Lambda, IAM, VPC), GCP basics
> **IaC:** Terraform, Ansible
> **CI/CD:** GitHub Actions, Jenkins, Argo CD
> **Observability:** Prometheus, Grafana, Loki, OpenTelemetry

### 6. CTA

> **Open to:** Senior DevOps / Platform Engineer roles, remote-first or Bengaluru-based. Reach me at firstname@email.com or DM.

---

## The Experience Section

- **3–5 bullets per role.** Most recent gets most detail.
- **Every bullet is STAR + XYZ.** "Did [X] using [Y], resulting in [Z] — for context S."
- **Attach media** to every role — certificates, project repos, blog posts, talks. This is LinkedIn's edge over a resume.
- **Active voice. No pronouns.**

### Before → After

| ✗ Before | ✓ After |
|----------|---------|
| Responsible for managing CI/CD | Automated CI/CD pipelines using Jenkins + Argo CD, enabling 15 daily deployments (up from 2/week) with zero-downtime releases |
| Worked on Kubernetes clusters | Migrated 12 microservices to EKS, reducing infra costs 40% and pod startup 90s → 12s |
| Managed monitoring | Built observability stack (Prometheus + Grafana + PagerDuty) across 50+ services, cutting MTTR 3 hours → 25 minutes |

---

## The Skills Section

- **Cap is 100 slots** (LinkedIn doubled it from 50 in early 2024). Don't write that the limit is 50.
- **Don't max out blindly.** Quality beats quantity — target 15–30 highly relevant skills with endorsements rather than 100 random ones.
- **Top 3 are pinned and disproportionately weighted.** Order them like a sentence: identity → specialty → edge.
- **Skills with ≥1 endorsement factor into search.** Skills with 0 endorsements are essentially invisible to ranking.
- **LinkedIn Skill Assessments are dead** (discontinued 2024, badges purged). Don't recommend them. The replacement is Verified Skills — anchor a skill to a verified workplace, education, or synced certification.

Recommended Top 3 by target role:

| Target | Top 3 (in order) |
|--------|------------------|
| DevOps Engineer | Kubernetes → AWS → Terraform |
| SRE | Kubernetes → Prometheus → Go (or Python) |
| Platform Engineer | Kubernetes → Terraform → Argo CD (or Backstage) |
| Cloud Architect | AWS (or Azure/GCP) → Terraform → Kubernetes |
| DevSecOps | Kubernetes → AWS Security → HashiCorp Vault |

---

## Verified Workplace (the modern credibility signal)

The 2024–2026 replacement for the dead Skill Assessment badges. Methods:

- **Microsoft Entra Verified ID** — if your employer has it set up. Strongest signal.
- **Work email** — verify a corporate email; LinkedIn confirms employer.
- **Government-issued ID** for identity verification.
- **Company-issued LinkedIn Learning or Recruiter license** also serves as workplace proof.
- **Synced certifications** — link AWS, GCP, Microsoft Learn, etc. into Licenses & Certifications and tag skills to them.

LinkedIn first-party claim: verified members see **~60% more profile views and ~50% more engagement** (cited via Microsoft Tech Community). 100M+ members verified by 2026. India is currently LinkedIn's lead market for the verification rollout.

---

## The Featured Section — recruiters scan it

**~70% of recruiters now browse the Featured section** to verify achievements before reaching out. It directly improves dwell-time on the profile, which feeds ranking.

Pin 3–5 strongest items, ordered strongest first:
- Best 1–2 posts (a viral one if you have it)
- A long-form article or newsletter
- Best project / GitHub repo with a strong README
- A certification announcement post
- A talk / slide deck / YouTube recording

Refresh every 3–6 months. Stale Featured items signal an inactive profile.

---

## Banner & Photo specs

- **Banner:** 1584 × 396 px, 4:1 ratio, ≤8 MB, JPG/PNG. Center 1350 × 220 px is the safe zone — sides crop on mobile and the profile photo overlays bottom-left. Use the banner for target-role keywords + 1 metric.
- **Photo:** LinkedIn first-party data — profiles with photos get **21× more views and 9× more connection requests**. 71% of recruiters admit they've rejected based on photo alone, so a good photo helps and a bad photo hurts more than no photo. Pay for a real headshot if budget allows.

---

## Recommendations

- **0** = yellow flag (recruiters suspect inactive/fake).
- **3–5** = minimum credibility (early career).
- **5–10** = sweet spot (mid-career).
- **10+** = strong signal — but only if specific and from credible recommenders. Generic "great to work with!" from junior peers is discounted.

How to ask: send a message naming the specific project/trait. *"Could you write 2–3 lines about [the migration / the on-call work / the X you saw me do]?"* Specific > generic. Avoid 1:1 reciprocal trades on the same date — recruiters spot them as padding.

---

## Custom URL — Google SEO, not LinkedIn search

A custom URL (`linkedin.com/in/firstname-lastname`) **does not affect LinkedIn's internal search ranking.** Its real value is Google SEO — when a recruiter googles your name pre-interview, a clean URL is what surfaces. Set this once.

---

## SSI (Social Selling Index) — what it actually is

SSI is LinkedIn's 0–100 metric, 4 pillars × 25 each, computed daily over a trailing 90-day window. URL: **`linkedin.com/sales/ssi`** — free for any LinkedIn member; the deeper drill-down dashboard requires Premium/Sales Nav, but the headline number is free.

**Critical context:** SSI is **only visible to the user themselves.** Recruiters do not see your SSI score in Recruiter. The "high SSI = better recruiter ranking" framing is largely marketing — but the underlying behaviors that lift SSI (complete profile, posting, engagement, network growth) ARE the same behaviors that feed Recruiter Spotlights and search ranking. So: SSI is a useful **diagnostic**, not a direct **ranking lever**. Even LinkedIn now de-emphasizes it ("Less scoring, more selling").

LinkedIn doesn't publish official tier benchmarks. Common heuristics:

- Average user: 40–50
- Active: 60–70
- Top 25%: ~65+ (industry-dependent)
- Top 10% / thought-leader: 75–80+

### The 4 Pillars (25 points each)

#### Pillar 1: Establish your professional brand

What it measures: profile completeness, Featured section, recommendations, verified credentials, long-form content.

**Actions:**
- Complete profile to All-Star (one-time)
- Pin 3–5 items to Featured (one-time, refresh quarterly)
- Get workplace verified via Entra (one-time)
- Sync 2–5 certifications into Licenses & Certifications (ongoing as you earn)
- 5–10 recommendations (refresh annually)
- 1 long-form article or newsletter per month (ongoing)

#### Pillar 2: Find the right people

What it measures: search usage, profile views.

**Daily:** view 10–15 profiles in target companies / ICP.

#### Pillar 3: Engage with insights

What it measures: posts, comments, reactions.

**Daily:** comment substantively on 3–5 posts. Aim for thread participation — back-and-forth with 3+ people drives the strongest reach amplification (~5×).

**Weekly:** 2–5 posts. Mix:
- 1 carousel or poll (highest relative reach)
- 1 personal-story or lesson-learned text post
- 1 technical short-form (code snippet, quick tip)

Skip external links in body when possible; if essential, native articles/newsletters bypass the discussion entirely.

#### Pillar 4: Build relationships

What it measures: quality connections, message activity, decision-maker reach.

**Weekly:** 2–3 personalized connection requests to decision-makers. No template spam.

**Daily:** respond to DMs within 24 hours.

### Realistic 30-day timeline

From an inactive baseline:
- **Week 1:** Profile completeness, Featured, workplace verification, request 2 recommendations. Daily: view 10 profiles.
- **Week 2:** Add daily engagement — comment substantively on 3–5 posts/day.
- **Week 3:** Start posting — 2 posts (1 carousel/poll + 1 text).
- **Week 4:** Send 3 personalized connection requests to hiring managers.

**Expected lift:** +15–25 SSI points by day 30. Reaching 70+ takes 30–45 days of sustained activity. Reaching 80+ takes months and a content presence.

---

## Recruiter red flags (2024–2026)

- **Dead profile** — no activity, blank Featured, recommendations from 5 years ago. Falls out of Spotlight surfacing.
- **Headline is just a job title and company.** Wastes the heaviest-weighted ranking field.
- **About starts with "Hi, I'm…" or "Results-driven…"** Reader doesn't expand.
- **Date / title / company mismatches between LinkedIn and resume.** Recruiters cross-check; ATS doesn't (myth) but humans do.
- **Zero recommendations** — especially fatal at senior level.
- **Public Open-to-Work green ring on a senior profile** — sometimes reads as desperation; recruiter-only mode is the safer default at senior level.
- **Stock photo or no photo** — 21× cost in views per LinkedIn first-party data.
- **Skills not backed by Experience evidence** — claiming "Kubernetes" with no K8s in any role description.
- **Engagement-pod patterns** — same accounts engaging in same order. 60–90 day shadow-ban risk.
