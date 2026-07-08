# /ats-check - ATS Parseability & Keyword Match

Analyze a CV against a job posting URL. Verifies what an ATS parser reads from the PDF's text layer and scores keyword coverage against the posting. Writes a markdown report with status and concrete improvements.

**Requires exactly 2 arguments:** `$ARGUMENTS` = `<cv-path> <posting-url>`

Examples:

```
/ats-check documents/cv/cv_pomelo_spanish.pdf https://www.linkedin.com/jobs/view/1234567890
/ats-check cv/main_pomelo.tex https://jobs.lever.co/company/abc123
```

If either argument is missing, ask the user for both before continuing.

---

## Execute the skill

Follow **every step** in `.claude/skills/ats-check/SKILL.md`. Do not skip steps.

**Shared verification rules:** `.claude/skills/job-application-assistant/08-ats-verification.md`

**Profile reference (missing have-it vs gap only):** `.claude/skills/job-application-assistant/01-candidate-profile.md`

---

## Quick reference

| Input | Action |
|-------|--------|
| `.pdf` | Use directly |
| `.tex` | Compile with `lualatex`, then use `.pdf` |
| LinkedIn URL | `bun run .agents/skills/linkedin-search/cli/src/cli.ts detail "<url>" --format plain` |
| Other URL | `WebFetch` |
| CV text | `pdftotext -layout` (degrade gracefully if missing) |

**Output file:** `ats-check/report-YYYY-MM-DD-<company-slug>-<role-slug>.md`

After saving, tell the user the report path and print a 3-line summary (parseability, keyword match %, top improvement).
