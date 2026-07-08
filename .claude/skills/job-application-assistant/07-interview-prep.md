# Interview Preparation Guide

## STAR Format

Structure answers as: **Situation** (context), **Task** (your responsibility), **Action** (what you did), **Result** (outcome).

Keep answers to 1-2 minutes. Be specific. End with what you learned or would do differently.

## Ready-Made STAR Examples

### 1. AYI Group Monolith-to-Microservices Migration (Architectural Leadership)
**S:** AYI Group operated a legacy monolithic application that limited scalability and made deployments risky — any change could break the entire system.
**T:** Lead the architectural migration to a modern, independently deployable architecture without disrupting ongoing business operations.
**A:** Designed and executed the migration to Java/Spring Boot microservices with React microfrontends. Defined service boundaries, established deployment pipelines, and coordinated incremental cutover to reduce risk.
**R:** Improved system scalability and significantly reduced deployment risk. MySQL optimizations during the same period cut average database response times by ~35% under peak load.
**Use for:** "Tell me about a technical decision you led", "Describe a migration you managed", "How do you reduce deployment risk?"

### 2. Sovos Tax Microservices as Tech Lead (Team Leadership & Distributed Systems)
**S:** Sovos needed a reliable, multi-jurisdiction tax calculation platform for hundreds of retail POS clients, with high availability requirements across distributed environments.
**T:** As Tech Lead of a 4–6 engineer team, architect and deliver tax-calculation microservices while mentoring the team and improving delivery predictability.
**A:** Architected Java/Spring Boot microservices with RabbitMQ for async processing. Established Jenkins CI/CD pipelines across teams. Led a Snowflake–Kafka PoC to evaluate real-time data integration. Mentored engineers on design patterns and code quality.
**R:** Platform served hundreds of enterprise retail clients with high availability. PoC demonstrated ~50% processing throughput improvement. Team delivery became more predictable over 5+ years in the role.
**Use for:** "Tell me about leading a team", "Describe a distributed system you built", "How do you mentor engineers?"

### 3. Mercado Libre Acquirer APIs in Go (Offline Reconciliation / Reliability)
**S:** MercadoPago's acquirer operations needed Go services to process daily Visa offline transaction files, validate APIs under production-scale load, and onboard sellers with correct fiscal classification.
**T:** Build and harden Go REST APIs for offline reconciliation, production reliability, and seller onboarding within a ~6-month engagement.
**A:** Built a Go API to ingest daily Visa offline CSV files and compute financial impact for downstream reconciliation workflows. Ran Artillery stress tests (internal "Bazoka" suite), monitoring peak load and failures primarily in Datadog (with New Relic for select metrics), and validated production auto-scaling under high transaction volume. Built a seller onboarding API classifying merchants by size (large, medium, small) with DynamoDB-backed CUIL lookup and segment-specific tax rules.
**R:** Reliable ingestion and impact calculation for offline Visa batches; production behavior validated under stress with observable peaks and scaling; sellers onboarded with correct fiscal segmentation.
**Use for:** "Fintech or acquirer experience", "Go in production", "How do you test high-volume APIs?", "Observability and reliability in production"

### 4. Siltium International Shipment Platform (NestJS / Impact)
**S:** Correo Argentino needed centralized management of international shipment data, with manual processes creating traceability gaps and operational overhead.
**T:** Build a centralized Node.js/TypeScript (NestJS) application to register and manage shipment data end-to-end.
**A:** Designed a high-throughput NestJS platform with clean architecture and a REST API layer for multiple internal clients; automated integration and validation across the shipment lifecycle.
**R:** Reduced manual processing workload by approximately 70% and eliminated recurring data entry errors.
**Use for:** "Recent project you're proud of", "Node.js/TypeScript experience", "How do you measure impact?"

### 5. Globant / JP Morgan Chase Security Remediation (Regulated Environment)
**S:** Spring Boot microservices in a JP Morgan Chase engagement had critical security vulnerabilities flagged by Veracode static analysis, posing compliance risk in a regulated banking environment.
**T:** Remediate vulnerabilities and improve dependency management without disrupting the release cycle.
**A:** Analyzed Veracode findings, updated Maven dependencies, patched vulnerable libraries, and validated fixes through testing and packaging before deployment.
**R:** Reduced critical CVE exposure. Successfully deployed remediated microservices in the regulated banking pipeline.
**Use for:** "Experience in regulated environments", "How do you handle security", "Working under compliance constraints"

## STAR Candidates (Complete Manually)

### Sovos Principal — API / batch latency 1s → 100ms
**Source:** LinkedIn / Martin_Grellet.pdf - Principal Software Engineer, Sovos (Jul 2022 – Jul 2024)
**What happened:** Rebuilt batch processing pipelines across Java microservices, cutting average API response times under high concurrency from ~1s to ~100ms.
**Why it matters:** Performance optimization, high-concurrency systems, measurable impact questions
**S/T/A/R stub:**
- Situation:
- Task:
- Action:
- Result:

### Siltium — clean architecture REST layer for multiple clients
**Source:** LinkedIn / Martin_Grellet.pdf - Software Engineer, Siltium (Mar 2025 – Present)
**What happened:** Built a NestJS REST API with clean architecture consumed by multiple internal clients while cutting manual workload ~70%.
**Why it matters:** Architecture standards, NestJS depth, collaboration across teams
**S/T/A/R stub:**
- Situation:
- Task:
- Action:
- Result:

### Mercado Libre — Visa offline reconciliation, stress testing, seller onboarding
**Source:** `01-candidate-profile.md` — Software Engineer, Mercado Libre (Sep 2021 – Mar 2022)
**What happened:** Built a Go API to ingest daily Visa offline transaction CSV files for financial impact and downstream reconciliation. Ran Artillery ("Bazoka") stress tests with Datadog (primary) and New Relic (select metrics), validating auto-scaling under peak load. Built seller onboarding API with DynamoDB (CUIL → entity) and segment-specific tax rules.
**Why it matters:** Acquirer/offline reconciliation exposure, Go in production, observability tooling, fiscal onboarding at scale
**S/T/A/R stub:**
- Situation:
- Task:
- Action:
- Result:

## Common Tough Questions

### "Why did you leave [previous company]?"
> Prepare per transition. General framing: each move pursued greater technical scope — from tax compliance leadership at Sovos to acquirer/reconciliation exposure at Mercado Libre, banking rigor at Globant/JPMC, full-stack migration at AYI, and current logistics/traceability work at Siltium. Always forward-looking; no negativity about former employers.

### "You don't have [specific skill/experience]."
> Acknowledge the gap honestly. Bridge to adjacent experience: e.g., limited AWS/GCP on CV but strong CI/CD, Docker, and distributed systems foundation; willing to certify or ramp quickly. Use Mercado Libre (Go) and Siltium (NestJS) as evidence of learning new stacks under production pressure.

### "Where do you see yourself in 5 years?"
> Staff/principal engineer with continued hands-on backend depth. Continue building high-scale distributed systems in fintech, compliance, or platform engineering.

### "What's your biggest weakness?"
> Example: tendency to dive deep into technical optimization — mitigated by time-boxing spikes, communicating trade-offs early to stakeholders, and delegating when leading a team.

### "Why this company specifically?"
> Customize per company. Must reference: specific projects, company values, market position, or team structure. Never give a generic answer.

## Questions You Should Ask Interviewers

### About the Role
- "What does a typical week look like in this role?"
- "What would success look like in the first 6 months?"
- "What's the biggest challenge the team is facing right now?"

### About the Team
- "How big is the team, and how do you divide work?"
- "What does the development/project lifecycle look like, from idea to production?"
- "How do you onboard new team members?"

### About Tech & Growth
- "What's your current tech stack for [relevant area]?"
- "Is there room to grow into more architectural or strategic decisions?"
- "How does the team stay current with new tools and methods?"

### About Culture (use these to prevent disappointment)
- "How would you describe the team culture?"
- "What does professional development look like here?"
- "Is there flexibility for remote/hybrid work?"
- "What's the balance between development/new projects and maintenance work?"
- "How would you describe the leadership style in this team?"
- "What do people who thrive here have in common?"

## Phone/Video Interview Tips
- Have STAR examples written out (use this file)
- Keep a glass of water nearby
- Smile when speaking (it changes your tone)
- Ask for clarification if a question is vague
- It's OK to take 5 seconds to think before answering
- End with: "Is there anything else you'd like to know about my background?"

## After the Application (Best Practice)

### Follow-Up Etiquette
- **Don't call to "stand out"** or to learn more about the role post-submission - this risks a negative impression
- If the employer specified a timeline, respect it and wait
- If no timeline was given and significant time has passed (2+ weeks), a brief call to ask about status is acceptable
- If you have genuinely new, relevant information to share, a short follow-up is fine

### Thank-You Notes
- When you receive any update (interview invitation, rejection, or status update), send a brief thank-you message
- Express appreciation for their time and the process
- Keep it short (2-3 sentences)

## Roleplay Guidelines
When the user asks for interview practice:
1. Ask which role/company to simulate
2. Start with easy warm-up questions ("Tell me about yourself")
3. Progress to role-specific technical questions
4. Include 1-2 behavioral questions using the competencies from the job posting
5. End with a tough question or curveball
6. After each answer, give brief feedback: what worked, what to sharpen
7. Suggest which STAR example would work best for each question
