# Search Queries for Job Scraper

<!-- Customized for Martín Alejandro Grellet — Yerba Buena, Tucumán, Argentina. Remote/LATAM focus. -->

## Search Sites

Primary (Argentina / LATAM):
- **linkedin.com/jobs** - LinkedIn job listings (filter: Argentina, Remote, Latin America)
- **zonajobs.com.ar** - major Argentine job board
- **bumeran.com.ar** - Argentine job board (IT section)
- **computrabajo.com.ar** - LATAM job board with Argentina filter
- **getonbrd.com** - remote tech jobs (LATAM-focused)

Secondary (remote global):
- **linkedin.com/jobs** - filter: Remote + "Latin America" or "Argentina"
- **welcometothejungle.com** - global tech (remote filter)
- Direct Google searches with `site:` filters for target companies (Mercado Libre, Globant, Sovos, etc.)

Note: Built-in CLI tools in `.agents/skills/` target Danish portals (Jobindex, Jobbank, Jobdanmark, Jobnet). For Argentina, prefer LinkedIn and the sites above, or add custom portal integrations via `/add-portal`.

## Query Categories

Queries grouped by priority. Combine with location terms ("Argentina", "Tucumán", "Yerba Buena", "Remote", "LATAM") where the site supports it.

### Priority 1: Senior Backend in Fintech

Primary career direction: Senior Backend Engineer at fintechs (payments, wallets, processors, neobanks).

```
site:linkedin.com/jobs "Senior Backend Engineer" fintech OR payments remote Argentina
site:linkedin.com/jobs "Senior Software Engineer" Java Spring Boot payments OR fintech Argentina
site:linkedin.com/jobs "Backend Engineer" MercadoPago OR "digital wallet" OR neobank remote
site:getonbrd.com "backend" OR "software engineer" fintech OR payments remote
```

### Priority 2: Senior Backend (stack-first, any strong domain)

Same role type; stack keywords when the posting does not say "fintech".

```
site:linkedin.com/jobs "Senior Software Engineer" Java Spring Boot remote Argentina
site:linkedin.com/jobs "Senior Backend Engineer" Java Spring Boot Argentina
site:linkedin.com/jobs "Backend Engineer" microservices NestJS OR Go remote Argentina
site:linkedin.com/jobs "payment" "software engineer" Go OR Java remote Argentina
```

### Priority 3: Adjacent domains (secondary)

Tax/compliance SaaS and regulated banking — apply when fit is strong, secondary to fintech search.

```
site:linkedin.com/jobs "Software Engineer" tax compliance OR regulatory remote Argentina
site:linkedin.com/jobs "Software Engineer" banking OR "payment processing" Java remote LATAM
site:linkedin.com/jobs "Ingeniero de software" backend Java remoto Argentina
```

### Priority 4: Broader net (Full Stack / Platform)

```
site:linkedin.com/jobs "Full Stack Engineer" Java React remote Argentina
site:linkedin.com/jobs "Platform Engineer" microservices remote LATAM
site:linkedin.com/jobs NestJS OR "Node.js" "software engineer" remote Argentina
site:linkedin.com/jobs "software engineer" Go microservices remote
```

## Target companies to monitor (fintech focus)

Monitor careers pages / LinkedIn company jobs when scraping (remote Argentina or Tucumán only):
- Mercado Libre / MercadoPago
- Ualá
- Lemon Cash
- Belo / other LATAM crypto-fintech if remote-friendly
- Bind / bancas digitales / neobanks hiring remote in AR
- Payment processors and wallet platforms (LATAM) with Argentina-based remote contracts

Also secondary (non-fintech but strong fit history): Sovos, Globant (JPMC-style banking pods) if role is Senior Backend and location allows.

## Location Filter

Hard filter — **no relocation**:
- **Ideal:** Fully remote within Argentina
- **Acceptable:** Hybrid or on-site in Tucumán / Yerba Buena only
- **Borderline:** Remote LATAM/global with Argentina-based contract (confirm timezone and legal setup)
- **Too far / FAIL:** On-site or hybrid outside Tucumán (e.g. Buenos Aires, Córdoba); any relocation requirement
## Date Filter

Only include jobs posted within the last 14 days, or with an application deadline that has not yet passed. If a posting date cannot be determined, include it but flag as "date unknown".

## Adapting Queries

If the user specifies a focus area, select queries from the matching category and also generate 2-3 custom queries for that focus. For example:
- "/scrape fintech" -> Priority 2 queries + custom fintech-specific queries
- "/setup --section search" -> reconfigure this file without redoing the full profile

## Suggested Role Types to Consider

Based on skill profile, also consider (secondary to Senior Backend):
- **Solutions Engineer / Technical Consultant** — domain expertise in tax/compliance and fintech
- **Integration Engineer** — POS, Kafka, RabbitMQ, API integration background
- **Staff / Principal Engineer** — deep Java + distributed systems track record
