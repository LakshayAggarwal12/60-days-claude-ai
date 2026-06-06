# 📄 Day 6 — ABTalksOnAI Claude Challenge
**Topic:** AI-Powered ATS Resume Optimization with Claude  
**Date:** June 6, 2026  
**Challenge:** #ABTalksOnAI | #ClaudeChallenge  

---

## 🎯 What I Did Today

Used Claude (claude.ai) to analyze, score, and fully rewrite my resume for maximum **ATS (Applicant Tracking System)** compatibility and recruiter readability — without inventing a single fake achievement.

The entire workflow: upload → analyze → score → rewrite → export as a PDF-ready, one-page A4 document, plus a visual ATS breakdown dashboard.

---

## 📁 Files

| File | Description |
|---|---|
| [Original resume (uploaded)](./lakshay-resume-sd-may.pdf)
| [Optimized ATS resume (Claude-generated PDF)](./Lakshay_Aggarwal_ATS_Resume.pdf)

---

## 📊 ATS Score Summary

| Metric | Before | After |
|---|---|---|
| **Overall Score** | 52 / 100 | 87 / 100 |
| **Score Gain** | — | +35 pts |
| Keyword Density | 40 | 80 |
| Formatting | 55 | 95 |
| Section Structure | 60 | 90 |
| Action Verbs | 45 | 85 |
| Contact Info | 70 | 95 |
| Summary Section | 0 | 85 |

---

## 🔴 Original Resume — Key Problems

These issues were identified by Claude from the raw PDF:

1. **No professional summary** — The top third of the resume was blank of keywords. ATS parsers weight this section the most.
2. **Weak action verbs** — Bullets opened with "Worked on," "Built," and "Applied" — passive and low-impact.
3. **Non-standard section headings** — Custom labels like "Achievements & Extracurriculars" don't map cleanly to ATS field parsers.
4. **Contact info not fully parseable** — LinkedIn and GitHub were listed as icon-style placeholders with no real URLs.
5. **Skills listed as a flat blob** — No category labels, so ATS couldn't bucket them into "Frontend," "Backend," or "AI/ML" dimensions.
6. **Bullet points lacked context** — Each bullet stated *what* was done but not *why* or *what outcome it drove*.
7. **CGPA buried in text** — Formatted inconsistently, making it harder for GPA-filtering ATS systems to extract it.

---

## 🟢 Optimized Resume — What Changed

### 1. Professional Summary Added (+40 pts)
A keyword-dense opening paragraph was written using only real information from the resume. It front-loads:
- Tech stack (Python, JavaScript, React, Node.js, FastAPI)
- AI/ML context (LLM APIs, Gemini, generative AI)
- Achievements (100+ LeetCode, Top 20 of 400+ in hackathon)

### 2. Keyword Density Increased (+20 pts)
Added ATS-critical terms that were implied but never stated:
- `full-stack development`
- `data preprocessing`
- `inference pipeline`
- `NLP fundamentals`
- `model evaluation`
- `generative AI workflows`

### 3. Action Verbs Strengthened (+15 pts)
Every bullet now opens with a strong ownership verb:

| Before | After |
|---|---|
| Worked on applied Generative AI workflows | **Designed and implemented** end-to-end data processing pipelines |
| Built an AI-powered research assistant | **Engineered** an AI-powered research assistant |
| Integrated Gemini API | **Integrated** Gemini API to deliver contextual health insights |

### 4. Section Headings Standardised (+10 pts)
Renamed to canonical ATS labels that parsers recognize universally:
- → `Professional Summary`
- → `Technical Skills`
- → `Experience`
- → `Projects`
- → `Achievements & Extracurriculars`

### 5. Contact Info Made Fully Parseable (+8 pts)
Real, plain-text URLs added:
- `linkedin.com/in/lakshay-aggarwal-dev`
- `github.com/LakshayAggarwal12`

Split across two clean lines so nothing wraps or gets garbled during ATS parsing.

### 6. Skills Categorised with Labels (+7 pts)
```
Programming Languages:  C, C++, Python, JavaScript
Frontend Development:   HTML5, CSS3, React
Backend Development:    Node.js, FastAPI
AI & Machine Learning:  LLM API Integration (Gemini), Prompt Engineering, NLP Fundamentals, Data Preprocessing
Tools & Platforms:      Git, GitHub, MongoDB
```

### 7. PDF Formatting — ATS-Safe Rules Applied
- Single column layout
- No tables, columns, icons, images, or text boxes
- Plain text contact line
- Consistent heading hierarchy
- Fits on exactly one A4 page

---

## ⚠️ Remaining Gaps (Why Not 100/100)

The 13 remaining points require real-world additions Claude couldn't fabricate:

| Gap | Fix |
|---|---|
| No certifications | Check IBM PBEL for a completion certificate (Coursera / Credly) |
| No quantified metrics | Add rough numbers: "50+ patients monitored," "10K+ records processed" |
| No JD alignment | Paste a target job description → tailored resume can gain +10–15 pts |

---

## 🛠️ The Prompt I Used

```
You are an ATS optimization expert and resume writer.
Rewrite my resume for maximum ATS parsing and recruiter readability,
keeping every claim truthful to the source.

Output EXACTLY two parts:
PART 1 — ATS SCORE (Previous / Optimized / 5-8 bullets of what changed)
PART 2 — FINAL RESUME (PDF-ready, one-page A4, single column, no tables/icons/images)

Rules:
- Use ONLY information from the resume.
- Never invent achievements, projects, skills, certifications, or metrics.
- Use strong action verbs.
- Remove redundancy.
- Must fit on ONE A4 page.
```

---

## 💡 Key Learnings

### About ATS Systems
- ATS stands for **Applicant Tracking System** — software recruiters use to filter resumes before a human ever sees them.
- Most large companies (and many mid-size ones) route every application through ATS first.
- A resume scoring below ~60/100 on ATS is often filtered out automatically, regardless of the candidate's actual skill.

### About Resume Optimization
- **The professional summary is the single highest-impact section.** It's the first thing ATS parses and the first thing a recruiter reads. An empty top section is a major missed opportunity.
- **Implied skills don't count.** If your project used NLP but your resume doesn't say "NLP," the ATS won't know.
- **Verbs carry weight.** "Worked on" signals participation. "Engineered" signals ownership. ATS and recruiters both respond differently.
- **Flat skill lists lose category context.** Labelling skills by domain (Frontend, Backend, AI/ML) gives ATS parsers structured data to match against job descriptions.
- **Real URLs > placeholder text.** LinkedIn and GitHub icons without links are invisible to parsers.

### About Using Claude for This
- Claude can score, rewrite, and export a resume as a real PDF — not just suggest edits.
- The constraint "use ONLY information from the resume" is critical. Without it, AI can hallucinate credentials.
- Asking Claude to explain *why* each change raises the score makes the output educational, not just transactional.
- The visual ATS dashboard (radar chart + bar breakdown) was generated live in the chat using Claude's artifact/widget capability.
- Claude used Python + ReportLab to produce a properly formatted A4 PDF — no external tools needed.

### About the Challenge Workflow
- Upload PDF → Claude reads it
- Claude scores the original (52/100) against ATS criteria
- Claude rewrites with strict truthfulness rules
- Claude generates the PDF using code (ReportLab)
- Claude builds an interactive visual analysis dashboard
- Add real URLs → Claude rebuilds the PDF with corrected contact info
- Document everything → this file

---

## 🔗 Links

- LinkedIn: [linkedin.com/in/lakshay-aggarwal-dev](https://linkedin.com/in/lakshay-aggarwal-dev)
- GitHub: [github.com/LakshayAggarwal12](https://github.com/LakshayAggarwal12)
- Challenge hashtag: `#ABTalksOnAI` `#ClaudeChallenge` `#Day6`

---

*All resume content is truthful to the original source document. No achievements were fabricated.*