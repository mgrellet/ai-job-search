# ATS check reports

Markdown reports from `/ats-check` — one file per run.

## Usage

```
/ats-check <cv-path> <posting-url>
```

**Examples:**

```
/ats-check documents/cv/cv_pomelo_spanish.pdf https://www.linkedin.com/jobs/view/1234567890
/ats-check cv/main_pomelo.tex https://jobs.lever.co/company/role-id
```

## What you get

Each report includes:

- **Parseability** — what `pdftotext` extracts (contact details, ligatures, reading order)
- **Keyword coverage** — required/preferred terms from the posting vs CV text
- **What to Improve** — actionable fixes (and explicit “do not add” for genuine gaps)

Reports are named `report-YYYY-MM-DD-<company>-<role>.md`.

## When to use

- Before `/apply`, to sanity-check a CV you wrote or tailored manually
- After editing a `.tex` and recompiling, to confirm keywords and PDF text layer
- To compare the same CV against different postings (one report per run)

Full workflow documentation: [README.md](../README.md) → Quick start step 5 and [How `/ats-check` works](../README.md#how-atscheck-works).

Framework reference: `.claude/skills/job-application-assistant/08-ats-verification.md`.
