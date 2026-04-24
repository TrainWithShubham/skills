# ATS Rules — How Applicant Tracking Systems Actually Work

Use this reference when diagnosing ATS compatibility issues.

---

## The 3-stage ATS pipeline

1. **Parse** — ATS extracts text from the PDF/docx. Fancy formatting, tables, sidebars, and images are LOST at this stage. Anything inside an image (skills icons, photos, infographic-style headers) is invisible.

2. **Match** — ATS compares extracted keywords against the job description. Matching is usually literal string matching, not semantic. "Kubernetes" ≠ "K8s". "CI/CD" ≠ "continuous integration / continuous delivery" (though good systems tokenize). Include both forms.

3. **Score** — ATS ranks the resume against other applicants. The usual threshold for human review is ~80% keyword match. Below that, the resume never reaches a human.

---

## Formatting: DO and DON'T

| ✓ DO | ✗ DON'T |
|-------|---------|
| Single-column layout | Two-column or sidebar layouts (ATS can't parse reading order) |
| Standard fonts: Calibri, Arial, Georgia, Times | Fancy fonts, decorative scripts, colored text |
| Simple text-based PDF (or .docx if the JD specifies) | Scanned/image-based PDF, complex .pdf with heavy graphics |
| Consistent date format: "Jan 2023 – Present" | Mixed formats: 01/2023, January 2023, 2023-01 |
| Reverse-chronological order (most recent first) | Functional/skills-based format (recruiters hate it) |
| 0.5–1 inch margins, 10-12pt body text | Tiny margins to cram in more content |
| Standard section headings | Creative headings ("My Journey", "What I Bring") |
| Acronyms spelled out at least once | Abbreviations only ("AWS" without ever writing "Amazon Web Services") |

---

## Standard section headings that parse cleanly

ATS systems look for these canonical section names:

- **Experience** / **Work Experience** / **Professional Experience**
- **Education**
- **Skills** / **Technical Skills**
- **Projects** / **Personal Projects**
- **Certifications**
- **Summary** / **Professional Summary** / **Profile**
- **Publications** (if applicable)
- **Awards** / **Achievements**

Avoid: "My Career", "What I Do", "About Me", "Background Story", "Accomplishments & Impact" (just use "Experience" or "Achievements").

### Canonical section order

This is the order that recruiters and ATS both expect. Deviating confuses both.

**Fresher (0-1 year):**
1. Contact (name, email, phone, LinkedIn, GitHub, city)
2. Professional Summary
3. Education (with CGPA if ≥8/10 or 3.5/4.0)
4. Skills (categorized)
5. Projects
6. Experience / Internships
7. Certifications
8. Awards / Extracurriculars (optional)

**Experienced (2+ years):**
1. Contact
2. Professional Summary
3. Skills (categorized)
4. Experience (reverse-chronological, most recent gets most space)
5. Projects / Key Initiatives
6. Certifications
7. Education (pushed to bottom for 3+ yrs)

If a resume deviates significantly from this order (e.g., experienced candidate with Education on top, or certifications scattered through Experience), call it out explicitly.

---

## File format guidance

- **.docx** — Generally the safest format for ATS. Most systems parse it cleanly.
- **PDF (text-based)** — Works with modern ATS (Workday, Greenhouse, Lever). Preferred for preserving layout.
- **PDF (scanned / image-based)** — **Do not use.** The ATS sees nothing. This is an automatic fail.

If the JD specifies a format (e.g., "Please upload your resume as a PDF"), follow it.

---

## Things that are invisible to ATS

Assume ATS cannot see:
- Text inside images (skill icons with tool names written on them)
- Text inside text boxes in Word (when improperly structured)
- Content in headers and footers (sometimes stripped — put critical info in the body)
- Graphical elements (progress bars for skill levels, star ratings)
- Custom bullet glyphs (use standard bullets)

---

## How to test a resume against ATS

If the user wants to verify ATS compatibility beyond this review, recommend:
- **Jobscan.co** — paste resume + JD, get a match score
- **ResumeWorded.com** — free ATS-style review
- **TopResume** — free review

None of these are required if the skill has already scored the resume — they're just a second opinion.

---

## What "good" looks like

A high-ATS-compatibility resume is often visually boring. Single column, black text, standard sections, no icons, clear headers. It won't win design awards, but it will get through the filter. Design flourishes go on the portfolio site, not the resume.

---

## Red flags to call out explicitly

When you see any of these, flag them in "What's Failing" — they're usually the dominant cause of no callbacks:

- **Two-column layout with sidebar** — the sidebar text is often lost entirely by ATS parsers. Contact info in a sidebar = resume rejected for "incomplete data".
- **Skills shown as pie charts or progress bars** — literal skill text is gone.
- **Dark-mode resume** (black background, white text) — can cause parsing and printing issues; some ATS convert to grayscale and lose contrast.
- **Photo + name in a header image** — name lost, email lost.
- **"Contact" section that's just icons** — phone/email may only appear visually, not as text.
- **Experience entries stored as a table** — dates, titles, and descriptions get jumbled in parse order.
