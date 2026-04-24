# Scoring Rubric

The total score is 100 points across 5 dimensions. Each dimension has specific criteria and point deductions. Be consistent — the same issue should get the same deduction across reviews.

---

## Dimension 1: ATS Compatibility (25 points)

This measures whether an automated parser can extract the resume's content correctly. A resume that scores high here will successfully pass through applicant tracking systems before reaching a human.

**Start at 25 and subtract:**

| Issue | Deduction |
|-------|-----------|
| Multi-column or sidebar layout | -8 |
| Tables used for content (not just visual spacing) | -5 |
| Text rendered inside images or icons (skills/contact) | -5 |
| Non-standard section headings ("My Journey" vs "Experience") | -4 |
| Fancy fonts (non-Calibri/Arial/Georgia/Times) | -3 |
| Inconsistent date formats across roles | -2 |
| Acronyms not spelled out at least once ("AWS" without "Amazon Web Services") | -2 |
| Colored or light-gray text that parsers may skip | -2 |
| Resume title is literally "Resume" or "CV" at the top | -1 |
| Headers/footers containing critical info (phone, email) | -2 |
| File is image-based PDF (scanned, not text) | -15 (major fail) |

Floor at 0.

---

## Dimension 2: Keywords & JD Match (25 points)

This measures how well the resume's vocabulary mirrors the job description and industry-standard keywords.

**Scoring approach:**

1. Extract 15-25 keywords from the JD (tools, technologies, methodologies, soft skills).
2. Count how many appear in the resume (case-insensitive, word-boundary match).
3. Compute match rate: `keywords_matched / total_keywords`.

| Match rate | Points |
|-----------|--------|
| ≥90% | 25 |
| 80-89% | 22 |
| 70-79% | 18 |
| 60-69% | 14 |
| 50-59% | 10 |
| 40-49% | 6 |
| <40% | 3 |

**Additional deductions (can go below the tier):**
- Skills are one long comma-separated dump with no categorization: -3
- Only abbreviations or only full names (not both, e.g., only "K8s" never "Kubernetes"): -2
- Critical JD keyword appears only in skills list and not in experience bullets: -2 each (up to -4 total)

---

## Dimension 3: Impact & Metrics (20 points)

This measures whether experience bullets show outcomes and use active voice.

**Sample the experience section.** Count bullets.

For each bullet, classify:
- **Strong (STAR)** — Has action verb + tech + measurable outcome. E.g., "Migrated 12 microservices to EKS, reducing infra costs by 40%"
- **Partial** — Action verb + tech, no outcome. E.g., "Built CI/CD pipeline in Jenkins"
- **Weak** — Passive voice or pure responsibility. E.g., "Responsible for monitoring production systems"

Compute: `(strong * 1.0 + partial * 0.5) / total_bullets`

| Ratio | Points |
|-------|--------|
| ≥0.80 | 20 |
| 0.65-0.79 | 17 |
| 0.50-0.64 | 13 |
| 0.35-0.49 | 9 |
| 0.20-0.34 | 5 |
| <0.20 | 2 |

**Additional deductions:**
- Uses "Responsible for..." or "Worked on..." opener on any bullet: -1 per occurrence (cap -4)
- No numbers/percentages/scale anywhere in experience: -3
- Overuse of weak verbs (helped, assisted, supported) as primary action: -2
- First-person pronouns in bullets (I, me, we, my, our): -1 per bullet (cap -3). Resume bullets start with a power verb, not a subject.

**Level adjustment:**
- For freshers: be lenient. If they have internship bullets that are partial but honest, don't penalize hard.
- For seniors: be strict. A senior with no scale metrics is failing the role.

---

## Dimension 4: Structure & Length (15 points)

**Start at 15 and subtract:**

| Issue | Deduction |
|-------|-----------|
| Fresher resume >1 page | -4 |
| Experienced resume >2 pages | -4 |
| Not reverse-chronological in experience | -3 |
| Missing a projects section (freshers: fatal, -5; experienced: -3) | -3 to -5 |
| Education buried at bottom for freshers | -2 |
| Education at top for experienced (>2 yrs) | -2 |
| Functional/skills-based format (no clear chronological work history) | -5 |
| Dates missing for roles or education | -2 |
| Section order is chaotic (certs in middle of experience, etc.) | -2 |
| Most recent role gets less space than older roles | -2 |
| Any single role has 6+ bullets (bloat — aim for 3-5, more detail on recent, less on older) | -2 |
| Any role has only 1 bullet (underselling) | -1 |

Floor at 0.

**Level-specific weighting (from the masterclass):**
- Fresher ideal: Header 5% · Summary 10% · Skills 10% · Experience/Internships 20% · Projects 30% · Education 25%
- Experienced ideal: Header 5% · Summary 10% · Skills 10% · Experience 40% · Projects 20% · Education 15%

---

## Dimension 5: Contact & Professional Presence (15 points)

**Start at 15 and subtract:**

| Issue | Deduction |
|-------|-----------|
| Unprofessional email (coolboy123@, name_date_of_birth@) | -3 |
| Missing LinkedIn URL | -2 |
| Missing GitHub URL (critical for DevOps/engineering) | -3 |
| Generic LinkedIn URL (linkedin.com/in/abc-xyz-1234567) instead of customized | -1 |
| City/country missing entirely | -1 |
| Full street address included (privacy risk, irrelevant) | -1 |
| DOB, marital status, gender, religion listed | -2 |
| Photo on resume for non-India international role | -3 |
| Multiple phone numbers listed | -1 |
| Portfolio/blog mentioned but link broken or missing | -1 |
| For DevOps: GitHub has fewer than 3 public repos OR is empty | -2 |
| For international/remote targets: no timezone indicator | -1 |
| Quirky/non-standard job title ("DevOps Ninja", "Cloud Rockstar", "Code Jedi") | -2 |
| Candidate used a non-standard title at their previous role and didn't translate it to a standard one | -1 |

Floor at 0.

---

## Final grade mapping

| Total | Grade | Verdict |
|-------|-------|---------|
| 90-100 | A | Interview-ready. Apply with confidence. |
| 80-89 | B | Solid resume. Minor tweaks will push it to A. |
| 70-79 | C | Foundation is there but it's costing callbacks. Fix the priority issues. |
| 60-69 | D | Major rework needed. Likely getting filtered by ATS or skimmed past by recruiters. |
| <60 | F | The resume is actively hurting you. Rewrite before applying anywhere else. |

---

## Calibration reminders

- **Don't inflate.** A 75 should feel like "needs work" not "pretty good."
- **Don't crush.** A 60 should feel recoverable, not hopeless.
- **Adjust for level** on dimensions 3 (Impact) and 4 (Structure). A fresher without enterprise-scale metrics is normal.
- **Be consistent.** Two resumes with the same issues should get the same deductions.
