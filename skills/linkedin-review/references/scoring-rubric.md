# LinkedIn Scoring Rubric

The total score is 100 points across 6 dimensions. Be consistent — the same issue should get the same deduction across reviews. If no resume is provided, dimension 6 is not scored and the remaining 90 points scale to 100 (multiply each score by 100/90).

Numeric claims here trace to `references/sources.md`.

---

## Dimension 1: Completeness (15 points)

LinkedIn calls a fully-filled profile "All-Star" status — its own discoverability benchmark. The official LinkedIn Help Center confirms All-Star "improves discoverability"; widely-cited "27× more discoverable" / "40× more opportunities" multipliers don't appear on current LinkedIn-owned pages, so don't quote them as fact.

**Start at 15, subtract for missing elements:**

| Issue | Deduction |
|-------|-----------|
| Profile photo not confirmed (PDF often won't show — ask user; don't deduct without evidence). LinkedIn first-party data: photo drives 21× more views, 9× more connection requests | -2 if user confirms missing |
| No banner image (1584 × 396, center 1350 × 220 safe zone) | -1 |
| No Featured section (~70% of recruiters now scan it before Experience) | -2 |
| "About" section empty or <300 characters total | -3 |
| Experience section has ≥1 role with no description | -1 per bullet-less role (cap -3) |
| Education section empty | -1 |
| Skills section shows <15 skills (cap is 100 since early 2024 — but quality > quantity; aim for 15–30 highly relevant skills with endorsements) | -2 |
| Certifications section empty (for tech roles where certs matter) | -1 |
| No Open-to-Work configuration if actively job-seeking — note: recruiter-only mode gives ~3× InMail response lift over no signal at all (LinkedIn first-party data: 14.5% vs 4.6%) | -1 |
| Custom LinkedIn URL not set (Google SEO benefit only — does not affect LinkedIn internal search) | -1 |
| Workplace not verified (Microsoft Entra Verified ID or work-email verification — replaces the dead Skill Assessment badges as the modern credibility signal) | -1 |
| **India only:** Notice Period / Expected CTC fields not filled (Oct 2025 India-exclusive recruiter-only fields) | -1 |

Floor at 0.

---

## Dimension 2: Discoverability & Keywords (25 points)

LinkedIn's deployed LLM-based ranking systems (360Brew, JUDE for jobs, Post Embeddings for feed — all public; see `sources.md`) read the profile as a holistic entity, not just a keyword bag. Keywords still matter, but they need **semantic neighbors** (related skills + context) to read as genuine expertise.

**Scoring approach:**

1. Extract 15-25 keywords from the JD (tools, technologies, methodologies, industry terms).
2. Count how many appear in the profile (case-insensitive, across Headline + About + Experience + Skills).
3. Check semantic-entity coverage: for each major keyword, are there 2-3 related terms nearby? (E.g., "Terraform" paired with "AWS / IaC / Infrastructure-as-Code" = genuine. "Terraform" alone in a skills dump = shallow.)

**Base score from raw keyword match:**

| Match rate | Base points |
|-----------|--------|
| ≥90% | 22 |
| 80-89% | 19 |
| 70-79% | 16 |
| 60-69% | 12 |
| 50-59% | 8 |
| <50% | 4 |

**Add back +3 if semantic-entity coverage is strong** (most keywords have contextual neighbors).
**Cap at 25.**

**Additional deductions:**
- Top 3 skills in Skills section not aligned with JD priorities: -2 (top 3 are heavily weighted in search)
- Headline missing any JD keyword: -3 (headline is the highest-weighted field)
- Keywords appear in Skills section only, not in Experience bullets: -2
- Industry-standard acronyms used without full names ("K8s" never spelled out): -1

---

## Dimension 3: Headline & About Hook (20 points)

The Headline and the first 2-3 lines of the About section (what shows before "See more") are the two most-read strings on the entire profile. Weight them accordingly.

**Headline scoring (10 pts):**

| Criterion | Points |
|-----------|--------|
| Uses 180+ of 220 chars (making full use of the slot) | +3 |
| Contains the target role keyword (e.g., "DevOps Engineer") in the first 40 chars | +2 |
| Contains 2-3 specialty/technology keywords | +2 |
| Contains a value proposition, result, or differentiator (not just job title) | +3 |

Subtract:
- Headline is just job title + company ("Software Engineer at X"): -5 from above
- Headline uses quirky/unprofessional phrasing ("DevOps Ninja", "Cloud Rockstar"): -3
- Typos or grammar errors: -2

**About Hook scoring (10 pts):**

The first 2-3 lines (visible before the "See more" fold, roughly first 280-320 characters on desktop) must compel the click.

| Criterion | Points |
|-----------|--------|
| Opens with a concrete result, bold statement, or provocative question | +4 |
| Mentions target role or domain in first 2 lines | +2 |
| Avoids generic buzzwords ("passionate", "results-driven", "dynamic professional") in the hook | +2 |
| Whole About section is structured (not a wall of text) | +2 |

Subtract:
- About opens with "Results-driven [profession]…" or equivalent generic template: -5 from above
- Hook is a job history recap instead of a value prop: -3
- About section uses third person without reason (confusing in 2026): -1

---

## Dimension 4: Experience Quality (15 points)

Same philosophy as the resume — STAR bullets with metrics — but LinkedIn allows **media attachments** per role and has more flexibility on length.

Sample the experience section. For each bullet, classify:
- **Strong (STAR/XYZ+S)** — Action verb + tech + measurable outcome + optional specific context
- **Partial** — Action verb + tech, no outcome
- **Weak** — Passive voice, pure responsibility, or "I/we/my" pronouns

Compute: `(strong × 1.0 + partial × 0.5) / total_bullets`

| Ratio | Base points |
|-------|------|
| ≥0.80 | 13 |
| 0.65-0.79 | 11 |
| 0.50-0.64 | 9 |
| 0.35-0.49 | 6 |
| <0.35 | 3 |

**Add back up to +2 for LinkedIn-specific polish:**
- Media attached to ≥1 role (certs, project repos, articles, decks): +1
- Role descriptions use structured bullets, not walls of prose: +1

**Additional deductions:**
- Any role has 6+ bullets (bloat): -1
- "Responsible for..." opener: -1 per occurrence (cap -3)
- First-person pronouns (I, me, we, my, our) — LinkedIn is more forgiving than resume but still prefers active voice: -1 per 3 occurrences (cap -2)

---

## Dimension 5: Social Proof & Verified Credentials (15 points)

Three pillars: **recommendations, endorsements, and verified credentials.** Important update: LinkedIn discontinued Skill Assessments in 2024 and purged the badges. The modern verification mechanic is workplace verification (Microsoft Entra Verified ID or work-email) plus credential-anchored skills (synced certifications under Licenses & Certifications, with skills tagged to them).

**Scoring:**

| Criterion | Points |
|-----------|--------|
| Recommendations received: 10+ from credible recommenders | +5 |
| Recommendations received: 5–9 | +4 |
| Recommendations received: 3–4 | +3 |
| Recommendations received: 1–2 | +1 |
| Recommendations received: 0 | 0 (yellow flag — recruiters suspect inactive/fake) |
| Top 3 skills each have 5+ endorsements | +2 |
| Top 3 skills each have 20+ endorsements | +3 (instead of +2) |
| Has Verified Workplace badge (Entra / work email / company-issued license) | +2 |
| Has 3+ synced certifications under Licenses & Certifications | +2 |
| Recommendations from managers, leads, or senior colleagues (not peer trades) | +1 |

Cap at 15.

**Deductions:**
- Recommendations exchanged 1:1 with same person on the same date (reciprocal): −1 — obvious to recruiters
- Skills section padded with unrelated/trivial skills (Microsoft Word, Email, etc.): −1
- Skills with 0 endorsements (these don't factor into LinkedIn search anyway): noted but no deduction

---

## Dimension 6: Resume Consistency (10 points)

**Only scored if a resume PDF is also provided.** If not, redistribute these 10 points proportionally across the other 5 dimensions (multiply each score by 100/90).

Start at 10, subtract:

| Issue | Deduction |
|-------|-----------|
| Any role title differs between LinkedIn and resume | -2 per mismatch |
| Dates differ (start or end month off by more than 1) | -2 per mismatch |
| Company name differs (e.g., typo, acronym vs full name) | -1 per occurrence |
| Role on resume but missing from LinkedIn | -2 |
| Role on LinkedIn but missing from resume | -2 (less critical but still a red flag) |
| Summary/About section in radically different tone (e.g., resume formal, LinkedIn casual) | -1 |
| Skills lists diverge significantly (resume claims 10 tools, LinkedIn claims 40, or vice versa) | -1 |

Floor at 0.

**Note to reviewer:** Small differences in formatting (e.g., "Jan 2024" vs "January 2024") are not mismatches. Real mismatches are semantic (different titles, different dates, different companies). Flag, but don't double-penalize formatting.

---

## SSI Estimation (not scored into the 100)

Estimated SSI is a separate output, not part of the 100-point score. Use it to give the user a directional sense of their search-ranking potential.

### Pillar 1: Establish your professional brand (0-25)

Estimable from the PDF:
- All-Star completeness: +6
- Recommendations (10+): +5 / (5–9): +4 / (3–4): +3 / (1–2): +1
- Featured section populated (3–5 items): +3
- Has 1+ long-form article or newsletter published: +3
- Verified Workplace via Entra/work email: +2
- 3+ synced certifications under Licenses & Certifications: +1
- Custom LinkedIn URL: +1
- About section >1500 chars with structured sections + hook in first 200 chars: +5

Cap 25.

### Pillar 2: Find the right people (0-25) — requires self-report

Ask the user: how often do you search for profiles or view profiles of people in your target companies?

| Self-report | Points |
|-------------|--------|
| Daily (10+ profiles) | 20-25 |
| Few times a week | 10-15 |
| Rarely | 5 |
| Never | 0 |

### Pillar 3: Engage with insights (0-25) — requires self-report

Ask: how often do you post, and how many posts do you comment on per day?

| Self-report | Points |
|-------------|--------|
| Posts 4+/week + comments 5-10/day | 20-25 |
| Posts 2-3/week + comments 3-5/day | 12-18 |
| Posts occasionally + comments occasionally | 5-10 |
| Never posts or comments | 0-3 |

### Pillar 4: Build relationships (0-25) — requires self-report

Ask: how many connections do you have, and do you message / stay in touch with decision-makers in your space?

| Self-report | Points |
|-------------|--------|
| 500+ connections, active DMs with decision-makers | 20-25 |
| 500+ connections, occasional DMs | 12-18 |
| <500 connections, passive | 5-10 |
| <100 connections, no outreach | 0-3 |

Add the four pillars for estimated total SSI. Tell the user to check the real number at linkedin.com/sales/ssi.

---

## Grade mapping

| Total (out of 100) | Grade | Verdict |
|---|---|---|
| 90-100 | A | Recruiter-magnet profile. SSI likely 70+. |
| 80-89 | B | Strong foundation. Minor tweaks push it to A. |
| 70-79 | C | Solid but generic. 3-5 concrete fixes would make a real difference. |
| 60-69 | D | Major gaps. Profile is underperforming its potential. |
| <60 | F | Invisible to recruiter search. Full rewrite + 30-day activity plan needed. |
