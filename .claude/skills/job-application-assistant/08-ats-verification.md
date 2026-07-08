# ATS Verification Framework

Shared reference for `/apply` (Step 5d) and `/ats-check`. An ATS parser reads the PDF's embedded **text layer**, not the rendered page — a CV that looks fine can still extract as garbage.

---

## Prerequisites

### pdftotext (optional)

Run `pdftotext -v`. `pdftotext` (poppler) is not part of TeX distributions.

- **Available:** run the mechanical parseability checks below.
- **Missing:** print a one-line warning, skip parseability items, and run keyword coverage against a visual Read of the PDF instead. Note **degraded mode** in the report.

### PDF source

- If the input is `.pdf`, use it directly.
- If the input is `.tex`, compile first with **lualatex** in the file's directory (`pdflatex often fails on modern MiKTeX with fontawesome5 errors`). Use the resulting `.pdf` for all checks below.

---

## Step 1: Extract the text layer

```bash
pdftotext -layout "<path-to-cv.pdf>" "<path-to-cv.pdf>.ats-extract.txt"
```

Read the `.txt` file. Delete it when done (do not commit extract files).

---

## Step 2: Parseability checks

Report each item as **pass**, **warn**, or **fail**:

| Check | Pass | Warn / Fail |
|-------|------|-------------|
| **Text extracted** | Non-empty extraction, no `(cid:NNN)` markers, no `` replacement characters, no visible PDF text missing from extraction | Garbage runs or empty extraction → **fail** |
| **Email literal** | Email address appears as readable text (icon glyph noise like `Envelope` is harmless) | Email only in hyperlink/icon → **fail** |
| **Phone literal** | Phone digits appear as readable text (icon noise like `MOBILE-ALT` is harmless) | Phone only in icon → **warn** |
| **Reading order** | Section headings appear in visual sequence; lines from different sections are not interleaved | Scrambled order → **fail** (common with multi-column/sidebar templates) |
| **Dates** | Each role and degree has recognizable years in the extraction | Missing dates → **warn** |

**Overall parseability status:**

- **PASS** — all checks pass (warnings allowed only for phone if email is present)
- **WARN** — minor issues (e.g. phone icon-only) but core content and contact extract cleanly
- **FAIL** — garbled text, missing email, or scrambled reading order

Failures are template-level problems: fix in the `.tex` (e.g. print email as plain text), recompile, and re-extract.

### LaTeX ligature corruption (common with `article` + pdfLaTeX)

If `pdftotext` shows broken words like `offline` → `o ine`, `Snowflake` → `Snow ake`, `flujos` → `` ``, `Certified` → `Certi ed`, the PDF embeds **TeX ligatures** (`fl`, `fi`, `ff`) without a ToUnicode map that reconstructs them.

**Fix for pdfLaTeX custom CVs** (add to preamble, before `babel`):

```latex
\usepackage{lmodern}
\usepackage[T1]{fontenc}
\usepackage[protrusion=true,expansion=false]{microtype}
\DisableLigatures{encoding = *, family = * }
```

- `lmodern` supplies scalable fonts (required — `microtype` expansion alone fails on default EC bitmap fonts in MiKTeX).
- `DisableLigatures` stops `fl`/`fi`/`ff` glyph substitution so the text layer matches literal spelling.

**Alternative:** compile with **lualatex** + `fontspec` and an OpenType font (often extracts cleanly without disabling ligatures).

`pdfgentounicode=1` alone is **not** sufficient with default EC fonts — verify with `pdftotext` after every template change.

---

## Step 3: Extract posting keywords

From the job posting (already fetched), build a keyword list:

1. **Required** — skills, tools, and qualifications explicitly marked required, "must have", "mandatory", or in a "Requirements" section
2. **Preferred** — "nice to have", "preferred", "bonus", or equivalent section

Also capture: job title, company, posting language, and source URL.

Do not invent keywords not present in the posting. Include domain terms (e.g. "fintech", "payments") when the posting emphasizes them.

---

## Step 4: Keyword coverage

Match each keyword against the **extracted CV text** (or visual PDF read in degraded mode), in the **posting's language**. Where the CV covers the concept in another language, count as **synonym-only** and note the language difference.

| Status | Meaning |
|--------|---------|
| **covered** | Term appears verbatim or with trivial inflection |
| **synonym-only** | Concept present under a different term; if the posting's exact term is truthfully applicable per the candidate profile, recommend using the posting's term (ATS matching is often literal) |
| **missing (have it)** | Candidate genuinely has this skill (per `01-candidate-profile.md`) but the CV text never mentions it — recommend adding where it fits naturally, preferring experience bullets over the profile statement |
| **missing (gap)** | Genuine gap per profile — do **not** recommend stuffing; acknowledge in cover letter framing instead |

### Coverage scores (for the report)

- **Required coverage:** `covered + synonym-only` required keywords / total required keywords
- **Preferred coverage:** same for preferred keywords
- **Overall ATS keyword match:** weighted average (required counts double preferred)

These scores approximate keyword screening — they are **not** the employer's actual ATS score.

---

## Step 5: Improvement recommendations

Produce actionable items, grouped by priority:

1. **Parseability fixes** (if any fail/warn) — specific `.tex` changes
2. **Quick keyword wins** — `missing (have it)` items with suggested bullet/section
3. **Synonym tightening** — replace synonym with posting's exact term where truthful
4. **Do not add** — list `missing (gap)` items explicitly so the user does not over-stuff the CV

**Honesty rule:** Never suggest fabricating skills, experience, or achievements.

---

## Report template

Use this structure when writing the output markdown (see `/ats-check` for filename and save location):

```markdown
# ATS Check Report — YYYY-MM-DD

**CV:** `<path-to-cv>`
**Job:** <Title> @ <Company>
**Posting URL:** <url>
**Posting language:** <lang>
**Mode:** full | degraded (no pdftotext)

---

## Summary

| Metric | Value |
|--------|-------|
| Parseability | PASS / WARN / FAIL |
| Required keyword coverage | X% (N/M) |
| Preferred keyword coverage | X% (N/M) |
| Overall ATS keyword match | X% |

**Verdict:** [1-2 sentences: ready to submit / fix parseability first / strengthen keywords before applying]

---

## Parseability

| Check | Status | Detail |
|-------|--------|--------|
| Text extracted | ✅/⚠️/❌ | ... |
| Email literal | ✅/⚠️/❌ | ... |
| Phone literal | ✅/⚠️/❌ | ... |
| Reading order | ✅/⚠️/❌ | ... |
| Dates | ✅/⚠️/❌ | ... |

---

## Keyword Coverage

| Keyword | Priority | Status | Note |
|---------|----------|--------|------|
| ... | required/preferred | covered / synonym-only / missing (have it) / missing (gap) | ... |

---

## What to Improve

### Parseability (if applicable)
- ...

### Add to CV (missing but you have it)
- ...

### Use posting's exact term (synonym-only)
- ...

### Do not add (genuine gaps)
- ...

### Suggested next step
- [ ] ...
```
