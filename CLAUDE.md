# Job Application Assistant for Martín Alejandro Grellet

<!-- SETUP: This file is populated by running /setup -->
<!-- After running /setup, all [PLACEHOLDER] tokens will be replaced with your actual information -->

## Role
This repo is a job application workspace. Claude acts as a career advisor and application assistant for Martín Alejandro Grellet, helping with:
1. **Job fit evaluation** - Assess job postings against your profile (skills, experience, behavioral traits)
2. **CV tailoring** - Adapt existing CV templates (LaTeX/moderncv) to target specific roles
3. **Cover letter writing** - Draft targeted cover letters using existing templates (LaTeX)
4. **Interview preparation** - Prepare answers, questions, and talking points for interviews
5. **Career strategy** - Advise on positioning and personal branding

## Candidate Profile

<!-- This section is auto-populated by /setup. You can also fill it in manually. -->

### Identity
- **Name:** Martín Alejandro Grellet
- **Location:** Yerba Buena, Tucumán, Argentina — **solo Tucumán (on-site/híbrido) o remoto**; sin relocalización
- **Languages:** Spanish (native), English (full professional)
- **Status:** Employed — Software Engineer at Siltium / Silentium Apps SRL (Correo Argentino project), since Mar 2025
- **Target role:** Senior Backend Engineer (primary)
- **LinkedIn headline:** "Backend Engineer | Java · Node.js(NestJS) · Go | Distributed Systems"
- **Sector focus:** Fintechs first (pagos, wallets, processors, neobanks)
### Education
- **Bachelor's in Computer Engineering / Ingeniería en Informática** (Mar 2004 – Feb 2010, graduated 2010) - Universidad del Norte Santo Tomás de Aquino, Tucumán, Argentina

### Professional Experience
*(Employment dates aligned to `documents/references/historial-laboral.txt`; known brands mapped from razón social.)*

- **Software Engineer – Correo Argentino** (Mar 2025 - Present) - **Siltium / Silentium Apps SRL** (Remote, Argentina)
  - Building a high-throughput NestJS/TypeScript platform for international shipment data with clean architecture REST APIs
  - Reduced manual processing workload by ~70% and eliminated recurring data entry errors

- **Full Stack Software Engineer** (Jul 2024 - Feb 2025) - **AYI Group / Badi S.A.** (Remote, Argentina)
  - Led architectural migration from legacy monolith to microservices (Java/Spring Boot) and microfrontends (React)
  - Optimized MySQL query plans and indexing, cutting average DB response times by ~35% under peak load

- **Principal Software Engineer** (Jul 2022 - Jul 2024) - **Sovos / Sovos Compliance SA** (Tucumán, Argentina)
  - Built a multi-jurisdictional tax compliance engine for POS systems in Java/Spring Boot
  - Improved high-concurrency API latency from ~1s to ~100ms; standardized CI/CD with Azure DevOps and Jenkins

- **Java Software Designer – JP Morgan Chase** (Mar 2022 - Jul 2022) - **Globant / Sistemas Globales S.A.** (Tucumán, Argentina)
  - Remediated Veracode security vulnerabilities and improved Maven dependency management
  - Deployed Spring Boot microservices in a regulated banking environment

- **Software Engineer** (Sep 2021 - Mar 2022) - **Mercado Libre / MercadoLibre S.R.L.** (Remote, Argentina)
  - Built a Go REST API to ingest daily Visa offline transaction CSV files, computing financial impact for downstream reconciliation workflows
  - Ran Artillery stress tests (internal "Bazoka" suite) with Datadog (primary) and New Relic (select metrics), validating production auto-scaling under high transaction volume
  - Developed a Go REST API to onboard and classify MercadoPago sellers (large, medium, small) with DynamoDB-backed CUIL lookup and segment-specific tax rules

- **Software Engineer / Tech Lead** (Feb 2016 - Aug 2021) - **Sovos / Sovos Compliance SA** (Tucumán, Argentina)
  - Led cross-functional teams of 4–6 engineers; mentored and drove technical decisions
  - Architected tax-calculation microservices (Java/Spring Boot, RabbitMQ)
  - Led Snowflake–Kafka PoC improving processing throughput by ~50% in testing
  - Established CI/CD pipelines with Jenkins across multiple teams

- **Java Developer / Application Support** (Apr 2014 - Feb 2016) - **Hewlett-Packard** (Córdoba, Argentina)
  - Maintained SOAP/REST web services for American Airlines reservation systems
  - Provided 24/7 on-call production and UAT support

- **Java Software Developer** (May 2013 - Apr 2014) - **Globant / Sistemas Globales S.A.** (Yerba Buena, Tucumán)
  - Built an internal travel portal from scratch (Java 7, Spring 3, Hibernate/JPA, Thymeleaf/jQuery)

- **Earlier roles (2008–2013):** HITMedia / La Gaceta · Everis / NTT Data (incl. Movistar) · Hewlett-Packard · Citytech

### Technical Skills
- **Primary:** Java (8, 11, 17), Spring Boot, microservices architecture, REST APIs, Node.js (NestJS), TypeScript, Go
- **Secondary:** React, AngularJS (legacy), Hibernate/JPA, TypeORM, Kafka, RabbitMQ, Docker, CI/CD (Jenkins, Azure DevOps), Datadog, New Relic, Artillery
- **Domain:** Tax compliance & regulatory systems, fintech/acquirer operations (MercadoPago: Visa offline reconciliation, seller fiscal onboarding), high-volume transactional systems, POS tax integrations, banking (regulated environments), logistics/traceability
- **Software:** MySQL, PostgreSQL, SQL Server, Oracle, Snowflake, DynamoDB, Maven, Gradle, Git, JUnit, Mockito, Veracode

### Certifications
- **Oracle Certified Associate, Java SE 7 Programmer (1Z0-803)** - completed 2014

### Publications
- None listed

### Awards
- None listed

### Behavioral Profile
*(Sin assessment formal — PI, DISC, MBTI, etc. Perfil inferido de experiencia laboral y LinkedIn About.)*
- **Technical leadership** - Comfortable leading teams of 4–6 engineers, mentoring, and driving architectural decisions
- **Systems thinking** - Strong track record in migrations, performance optimization, and distributed architectures
- **Strengths:** Cross-functional collaboration, delivery predictability, regulated-environment experience (banking, fintech, tax compliance)
- **Growth areas:** Expanding depth in cloud-native platforms (AWS/GCP) and modern frontend beyond React basics — frame as active upskilling
- **Thrives in:** Teams with clear technical ownership, measurable impact, and hands-on backend depth; remote en Argentina o híbrido en Tucumán

### What Excites You
- Building scalable, high-performance distributed systems with measurable throughput and reliability gains
- Leading migrations from legacy monoliths to modern microservices architectures
- Working on systems with real transactional volume and regulatory stakes (fintech, tax, payments)

### Target Sectors
- **Primary — Fintech & payments:** Mercado Libre / MercadoPago-type platforms, payment processors, digital wallets, neobanks
- **Secondary — Tax & compliance / enterprise SaaS:** Sovos-type regulatory technology, POS integrations
- **Secondary — Banking & regulated tech:** JP Morgan Chase-type environments via consultancies or direct hire
- **Open — Logistics & traceability:** Correo Argentino-type shipment and tracking systems (current domain; secondary for search)

### Deal-breakers
- **Relocalización:** no. Solo Tucumán (on-site/híbrido) o remoto (Argentina / contrato desde Argentina)
- Sin mínimo salarial declarado aún
- Prioridad de sector: fintechs (pagos, wallets, processors, bancos digitales)

## Repo Structure
- `cv/` - LaTeX CV variants (moderncv template, banking style)
- `cover_letters/` - LaTeX cover letters (custom cover.cls template)
- `ats-check/` - Markdown reports from `/ats-check` (ATS parseability + keyword match)
- `.claude/skills/` - AI skill definitions for the application workflow
- `.agents/skills/` - Job search CLI tools

## Workflow for New Job Applications
1. User provides a job posting (URL or text)
2. **Always evaluate fit first**: skills match, experience match, behavioral/culture match. Present this assessment to the user before proceeding.
3. **Optional — `/ats-check`**: if the user already has a CV PDF/`.tex`, run `/ats-check <cv> <url>` before tailoring to get parseability status and keyword gaps (report saved to `ats-check/`). See `08-ats-verification.md`.
4. If good fit: create targeted CV (`cv/main_<company>.tex`) and cover letter (`cover_letters/cover_<company>_<role>.tex`)
5. **Verify both documents** (see Verification Checklist below)
6. Prepare interview talking points based on the role requirements and your strengths

**Important:** When mentioning agentic coding or AI tooling in CVs/cover letters, explicitly reference **Claude Code** by name.

## Verification Checklist
After creating or updating a CV or cover letter, re-read the generated file and verify **all** of the following before presenting to the user. Report the results as a pass/fail checklist.

### Factual accuracy
- [ ] All claims match actual profile (CLAUDE.md / candidate profile) - no fabricated skills, experience, or achievements
- [ ] Job titles, dates, company names, and locations are correct
- [ ] Contact details are correct
- [ ] All company-specific claims (partnerships, products, technology, expansions) have been independently verified via WebFetch/WebSearch - do not trust reviewer agent research without verification

### Targeting
- [ ] Profile statement / opening paragraph is tailored to the specific role (not generic)
- [ ] Skills and experience bullets are reframed to match the job requirements
- [ ] Key job requirements are addressed (with gaps acknowledged where relevant)
- [ ] Nice-to-have requirements are highlighted where there is a match

### Consistency
- [ ] CV follows the standard 2-page moderncv/banking format
- [ ] Cover letter uses cover.cls template and established structure
- [ ] Tone is consistent across CV and cover letter
- [ ] No contradictions between CV and cover letter content

### Quality
- [ ] No LaTeX syntax errors (balanced braces, correct commands)
- [ ] No spelling or grammar errors
- [ ] Agentic coding / AI tooling references mention **Claude Code** by name
- [ ] Cover letter is addressed to the correct person (or "Dear Hiring Manager" if unknown)
- [ ] Cover letter fits approximately one page

### Compiled PDF verification (MANDATORY - never skip)
Both documents MUST be compiled and visually inspected via the Read tool on the PDF output. "Looks fine in the .tex" is not acceptable - LaTeX page-break decisions are unpredictable. Iterate until these all pass:
- [ ] CV compiled with **lualatex** (pdflatex often fails on modern MiKTeX with fontawesome5 font-expansion errors). Cover letter compiled with **xelatex** (cover.cls requires fontspec).
- [ ] **CV is exactly 2 pages** - not 1, not 3
- [ ] **No orphaned `\cventry` titles** - a job/education title must never sit at the bottom of a page with its bullets spilling to the next page. Use `\needspace{5\baselineskip}` before each `\cventry` to prevent this, and `\enlargethispage{2-3\baselineskip}` to rescue a trailing section that just barely spills
- [ ] **Cover letter is exactly 1 page** - signature block must fit with the body, never overflow
- [ ] **Cover letter bullet font matches body font** - `\lettercontent{}` must not wrap `\begin{itemize}...\end{itemize}` (the command's trailing `\\` errors on `\end{itemize}`, and moving itemize outside loses the Raleway font). Standard pattern: close `\lettercontent{}`, then wrap the list in `{\raggedright\fontspec[Path = OpenFonts/fonts/raleway/]{Raleway-Medium}\fontsize{11pt}{13pt}\selectfont \begin{itemize}...\end{itemize}\par}`

### ATS & keyword verification (CV)
ATS parsers read the PDF's embedded text layer, not the rendered page. Extract it with `pdftotext -layout` and verify what a parser sees. `pdftotext` (poppler) is optional - if missing, skip the parseability items with a warning and check keyword coverage from the visual PDF read instead.
- [ ] CV text layer extracts cleanly - no `(cid:*)` markers, `` replacement characters, or text visible in the PDF but absent from the extraction
- [ ] Email and phone appear as **literal text** in the extraction (icon-glyph noise like `MOBILE-ALT`/`Envelope` is harmless, but a contact detail carried only by an icon or hyperlink is invisible to ATS)
- [ ] Reading order of the extracted text matches the visual order (single-column stock template is safe; multi-column custom templates are where this breaks)
- [ ] Posting keywords covered or honestly absent - synonym-only matches tightened to the posting's exact term where truthfully applicable, keywords the profile genuinely supports added to experience bullets, genuine gaps left visible and **never stuffed**
