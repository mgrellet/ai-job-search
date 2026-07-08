---
name: ats-check
description: >
  Analyzes a CV (PDF or LaTeX) against a job posting URL for ATS parseability and keyword
  coverage. Writes a markdown report with status and improvement recommendations. Triggers on:
  /ats-check, ats check, ATS analysis, parseabilidad cv, keyword match cv, revisar ats
allowed-tools: Read, Write, Glob, Grep, WebFetch, Bash(bun run .agents/skills/linkedin-search/cli/src/cli.ts *), Bash(pdftotext:*), Bash(lualatex:*)
---

# ATS Check

Analyzes what an ATS parser would see in a compiled CV PDF and how well its text matches a specific job posting. Compares against the **CV text layer**, not the candidate profile — a skill may exist in the profile but be invisible to the ATS if absent from the PDF.

**Output:** always save a report to `ats-check/report-YYYY-MM-DD-<company-slug>-<role-slug>.md`.

**Shared framework:** follow `.claude/skills/job-application-assistant/08-ats-verification.md` for parseability rules, keyword statuses, scoring, and report structure.

---

## Invocation (required: 2 parameters)

```
/ats-check <cv-path> <posting-url>
```

Examples:

```
/ats-check documents/cv/cv_pomelo_spanish.pdf https://www.linkedin.com/jobs/view/1234567890
/ats-check cv/main_pomelo.tex https://jobs.lever.co/company/role-id
```

Both parameters are **required**. If either is missing, ask the user before proceeding.

---

## Step 1: Parse and validate inputs

1. Split `$ARGUMENTS` (or the user's message) into **cv-path** and **posting-url**.
   - cv-path: `.pdf` or `.tex`
   - posting-url: `http://` or `https://`
2. Verify the CV file exists (Glob/Read). If not found, stop with a clear error.
3. Derive slugs for the report filename:
   - `cv-slug` from the CV basename (e.g. `cv_pomelo_spanish`)
   - `company-slug` and `role-slug` — filled after fetching the posting in Step 3

---

## Step 2: Prepare the PDF

### If input is `.pdf`

Use it as-is. Record the path for Step 4.

### If input is `.tex`

1. `cd` to the directory containing the `.tex` file.
2. Compile with lualatex:

```bash
lualatex -interaction=nonstopmode "<basename>.tex"
```

3. If compilation fails, report the error and stop — do not proceed with ATS analysis on an uncompiled source.
4. Use the resulting `.pdf` in the same directory.
5. Optionally delete `.aux`, `.log`, `.out` after a successful extract in Step 4 (keep `.tex` and `.pdf`).

---

## Step 3: Fetch the job posting

Choose the fetch method by URL:

### LinkedIn (`linkedin.com/jobs/` or `linkedin.com/job/`)

Use the **linkedin-search** CLI (reuse, do not reimplement):

```bash
bun run .agents/skills/linkedin-search/cli/src/cli.ts detail "<posting-url>" --format plain
```

If the command fails with `BAD_ID` (common when the URL has a trailing slash), retry with the numeric job ID extracted from the URL (e.g. `4424719977`) or strip the trailing slash. If both fail, try `WebFetch` on the URL once.

> **Personal use only** — keep volume low per linkedin-search ToS.

### All other URLs (Greenhouse, Lever, Ashby, company careers pages, etc.)

Use `WebFetch` on the posting URL.

If the fetch returns a login wall, empty body, or a generic listing page (not a single job), stop and ask the user to paste the posting text or provide a direct job URL.

### Extract from fetched content

- Job title, company name, location (if present)
- Posting language
- Required skills/qualifications
- Preferred/nice-to-have skills
- Key responsibilities (for context, not every word becomes a keyword)

Build the keyword list per **Step 3** in `08-ats-verification.md`.

---

## Step 4: Extract CV text layer

1. Run `pdftotext -v`. Set `mode` to `full` or `degraded` accordingly.
2. If **full**:

```bash
pdftotext -layout "<path-to-cv.pdf>" "<path-to-cv.pdf>.ats-extract.txt"
```

Read the extract file. Run parseability checks from `08-ats-verification.md` Step 2.

3. If **degraded**: Read the PDF visually and note degraded mode in the report. Skip mechanical parseability except what you can verify visually.

4. Delete `<path-to-cv.pdf>.ats-extract.txt` when done.

---

## Step 5: Keyword coverage and profile cross-check

1. Read `.claude/skills/job-application-assistant/01-candidate-profile.md` — used **only** to distinguish `missing (have it)` vs `missing (gap)`, not as the text being matched.
2. Match each posting keyword against the **CV extract** (or visual PDF in degraded mode).
3. Compute required/preferred/overall scores per `08-ats-verification.md` Step 4.
4. Build improvement recommendations per Step 5 of that file.

---

## Step 6: Write and save the report

1. Assemble the report using the template in `08-ats-verification.md` (Summary, Parseability, Keyword Coverage, What to Improve).
2. Save to:

```
ats-check/report-YYYY-MM-DD-<company-slug>-<role-slug>.md
```

Slugify: lowercase, spaces → hyphens, strip special characters.

Example: `ats-check/report-2026-07-08-pomelo-senior-backend-engineer.md`

3. Create the `ats-check/` directory if it does not exist.

4. Confirm to the user:

> Report saved to `ats-check/<filename>.md`. Review parseability status and "What to Improve" before submitting.

5. Print a short terminal summary: parseability status, overall keyword match %, and top 3 improvements.

---

## Important rules

1. **Two parameters required** — CV path and posting URL. No batch mode in v1.
2. **Always save the `.md` report** — do not skip Write even if the user only asked in chat.
3. **Never fabricate keywords or skills** — same honesty rule as `/apply`.
4. **CV text, not profile** — keyword match is against what the ATS reads from the PDF.
5. **Reuse linkedin-search** for LinkedIn URLs; use WebFetch for everything else.
6. **Clean up** temporary `.ats-extract.txt` files; do not commit them.

---

## Relationship to other commands

| Command | Overlap |
|---------|---------|
| `/apply` | Runs the same ATS checks (Step 5d) on a freshly drafted CV; references `08-ats-verification.md` |
| `/upskill` | Compares **profile** vs posting for learning gaps — not CV text vs posting |
| `/rank` | Batch job fit triage — no CV analysis |

After `/ats-check`, if keyword coverage is low, the user may run `/apply` to tailor the CV, or edit the `.tex` manually and re-run `/ats-check`.
