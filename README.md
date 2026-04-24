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

## Installation

```bash
npx skills add LondheShubham153/agent-skills
```

Or install a specific skill:

```bash
npx skills add LondheShubham153/agent-skills --skill resume-review
```

## Usage

After installation, trigger the skill by sharing a resume + job description with Claude:

```
/resume-review

JD: [paste job description]
Resume: /path/to/resume.pdf
```

Or naturally:

> "Can you review my resume? I'm applying for senior DevOps roles at US startups and not getting callbacks. Here's the JD: [...] and the resume is at ~/Desktop/resume.pdf"

The skill auto-triggers on phrases like "review my resume", "roast my resume", "check my CV", "is this resume good", "what's my ATS score", or "why am I getting ghosted".

## Requirements

- Resume must be provided as a **text-based PDF** (not scanned images)
- A **job description** is required — the review is tailored to the JD's keywords and seniority

## Repository structure

```
agent-skills/
├── README.md
├── LICENSE
└── skills/
    └── resume-review/
        ├── SKILL.md
        └── references/
            ├── scoring-rubric.md
            ├── devops-rules.md
            ├── ats-rules.md
            ├── keywords-bank.md
            └── market-specific.md
```

## Contributing

Issues and PRs welcome. If you have resume patterns that should be caught (new deadly sins, market-specific rules, keyword gaps), open an issue with an example.

## License

MIT — see [LICENSE](LICENSE).

## Credits

- Skill design and content: Shubham Londhe ([@LondheShubham153](https://github.com/LondheShubham153))
- Source material: the [TrainWithShubham Resume Masterclass](https://trainwithshubham.com)
- Built with the [Claude Code skill-creator](https://github.com/anthropics/claude-code)
