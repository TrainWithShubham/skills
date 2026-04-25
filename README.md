# TrainWithShubham Agent Skills

A collection of [Agent Skills](https://skills.sh) maintained by [Shubham Londhe](https://github.com/LondheShubham153) / [TrainWithShubham](https://trainwithshubham.com). Designed for real-world engineering workflows — especially DevOps, SRE, Cloud, and Platform engineering.

## Skills in this repo

### `resume-review`

Review a resume like a professional recruiter AND an ATS in one pass. Produces:

- A **Recruiter Verdict** — SHORTLISTED / BORDERLINE / LIKELY REJECTED / REJECTED
- An **ATS Score** out of 100 across 5 dimensions (ATS compatibility, keywords, impact/metrics, structure, contact)
- A **7 Deadly Sins** diagnostic (tool vomit, zero metrics, passive voice, generic summary, multi-page bloat, no projects, ignoring keywords)
- **Highlights and Lowlights** with direct resume quotes
- **JD match analysis** — keywords present, missing, and buried
- **Before → After bullet rewrites** using the STAR + XYZ+S formula
- **Your #1 Focus Next** — one concrete career investment to prioritize over the next 1–3 months
- An **empowering final recommendation** that names concrete alternative roles for candidates who are rejected

Especially strong for **DevOps, SRE, Cloud, Platform, and Infrastructure** resumes. Works for any technical resume. Covers **India**, **International**, and **Remote** market-specific rules (photo, CTC, timezone signals, GitHub activity, etc.).

Based on the [Resume Masterclass](https://trainwithshubham.com) — the "7 deadly sins", STAR formula, and keyword bank come from the workshop.

### `linkedin-review`

Review a LinkedIn profile the way three audiences would, together: a recruiter running searches, a career coach shaping the candidate's narrative, and LinkedIn's own ranking algorithm. Produces:

- A **Recruiter Verdict** — FOUND & CLICKED / FOUND, PASSED / NOT FOUND
- A **100-point score** across 6 dimensions (Completeness, Discoverability & Keywords, Headline & About Hook, Experience Quality, Social Proof & Verified Credentials, Resume Consistency)
- An **estimated SSI (Social Selling Index)** with the candor that SSI is self-only-visible — recruiters don't see it; the underlying behaviors are what feeds Recruiter Spotlights
- The **7 Deadly LinkedIn Sins** check
- **Highlights and Lowlights** with direct profile quotes
- **Headline rewrite** using a named formula (Belcak, Jeff Su two-part, or Justin Welsh — credited, not invented)
- **About section rewrite** with hook optimized for the ~200-char mobile / ~300-char desktop "See more" fold
- **Experience bullet rewrites** using STAR + XYZ
- A **LinkedIn ↔ Resume consistency check** if a resume is also provided
- A **30-day action plan** with daily / weekly / monthly habits — calibrated to realistic +15–25 SSI lift

Grounded in **2024–2026 cited sources**: LinkedIn's deployed LLM ranking systems (360Brew, JUDE, Post Embeddings), the Nov 2025 AI People Search launch, Van der Blom's 2025 Algorithm Insights Report, the real Recruiter Spotlight mechanic (Active Talent / More Likely to Respond), and the **Oct 2025 India-only Notice Period + Expected CTC fields**. Replaces 2022-era folklore (dead Skill Assessments, "27× more discoverable", "comments 15× weighted than likes") with current evidence — see `references/sources.md` for the full citation list.

Especially strong for **DevOps, SRE, Cloud, Platform, and Infrastructure** profiles. Works for any technical LinkedIn. Includes **India market** specifics: the Oct-2025 Notice Period field, Bengaluru-not-Bangalore canonical naming, public-CTC red flag, and India-fintech title-inflation detection.

## Installation

```bash
npx skills add TrainWithShubham/skills
```

Or install a specific skill:

```bash
npx skills add TrainWithShubham/skills --skill resume-review
npx skills add TrainWithShubham/skills --skill linkedin-review
```

## Usage

### `resume-review`

After installation, trigger the skill by sharing a resume + job description with Claude:

```
/resume-review

JD: [paste job description]
Resume: /path/to/resume.pdf
```

Or naturally:

> "Can you review my resume? I'm applying for senior DevOps roles at US startups and not getting callbacks. Here's the JD: [...] and the resume is at ~/Desktop/resume.pdf"

The skill auto-triggers on phrases like "review my resume", "roast my resume", "check my CV", "is this resume good", "what's my ATS score", or "why am I getting ghosted".

### `linkedin-review`

Export your LinkedIn profile via **More → Save to PDF** on your profile page, then share it with Claude alongside the target JD:

```
/linkedin-review

JD: [paste job description]
LinkedIn PDF: /path/to/Profile.pdf
Resume PDF (optional): /path/to/resume.pdf
```

Or naturally:

> "Can you audit my LinkedIn? I'm targeting senior DevRel roles at international DevTools companies — here's the profile PDF and the JD."

The skill auto-triggers on phrases like "review my LinkedIn", "audit my profile", "why am I not getting recruiter DMs", "is my LinkedIn good", or sharing a LinkedIn PDF without explicit instructions.

## Requirements

- Resume / LinkedIn profile must be provided as a **text-based PDF** (not scanned images). For LinkedIn, use **More → Save to PDF** on the profile page.
- A **job description** is required for `resume-review`. Strongly recommended for `linkedin-review` (drives keyword and semantic-entity scoring).

## Repository structure

```
skills/
├── README.md
├── LICENSE
└── skills/
    ├── resume-review/
    │   ├── SKILL.md
    │   └── references/
    │       ├── scoring-rubric.md
    │       ├── devops-rules.md
    │       ├── ats-rules.md
    │       ├── keywords-bank.md
    │       └── market-specific.md
    └── linkedin-review/
        ├── SKILL.md
        └── references/
            ├── scoring-rubric.md
            ├── linkedin-rules-and-ssi.md
            ├── market-specific.md
            ├── keywords-bank.md
            └── sources.md
```

## Contributing

Issues and PRs welcome. If you have resume patterns that should be caught (new deadly sins, market-specific rules, keyword gaps), open an issue with an example.

## License

MIT — see [LICENSE](LICENSE).

## Credits

- Skill design and content: Shubham Londhe ([@LondheShubham153](https://github.com/LondheShubham153))
- Source material: the [TrainWithShubham Resume Masterclass](https://trainwithshubham.com)
- Built with the [Claude Code skill-creator](https://github.com/anthropics/claude-code)
