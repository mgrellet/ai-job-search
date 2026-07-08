# Candidate Profile

## Identity
- **Name:** Martín Alejandro Grellet
- **Location:** Yerba Buena, Tucumán, Argentina
- **Phone:** +54 381 607 3574
- **Email:** martin.alejandro.grellet@gmail.com
- **LinkedIn:** https://www.linkedin.com/in/mgrellet
- **GitHub:** Omitted intentionally (no public link)
- **Languages:** Spanish (native), English (full professional)
- **Status:** Employed — Software Engineer at Siltium / Silentium Apps SRL (since Mar 2025)
- **Target role:** Senior Backend Engineer (primary; not actively targeting Engineering Manager)
- **Constraints:** Solo Tucumán (on-site/híbrido / Yerba Buena) o remoto. Sin relocalización a otra ciudad ni fuera de Argentina.
- **Target companies / sector focus:** Fintechs (pagos, wallets, processors, neobanks). Also open to tax/compliance SaaS and regulated banking.

## Education

| Degree | Period | Institution | Key Topics |
|--------|--------|-------------|------------|
| Bachelor's in Computer Engineering (Ingeniería en Informática) | Mar 2004 – Feb 2010 (graduated 2010) | Universidad del Norte Santo Tomás de Aquino, Tucumán, Argentina | Computer software engineering |

## Professional Experience

### Software Engineer – Correo Argentino - Siltium / Silentium Apps SRL (Mar 2025 - Present)
Remote, Argentina
- Designing and implementing a centralized, high-throughput backend platform using TypeScript and NestJS to register and manage international shipment data
- Building a RESTful API layer consumed by multiple internal clients, enforcing clean architecture patterns for long-term maintainability
- Automated data integration and validation workflows across the shipment lifecycle, reducing manual processing workload by ~70% and eliminating recurring data entry errors

### Full Stack Software Engineer - AYI Group / Badi S.A. (Jul 2024 - Feb 2025)
Remote, Argentina
- Led architectural migration from legacy monolith to microservices (Java/Spring Boot) and microfrontends (React), improving independent deployability and reducing deployment risk
- Optimized MySQL query plans and indexing strategies, cutting average database response times by ~35% under peak load

### Principal Software Engineer - Sovos / Sovos Compliance SA (Jul 2022 - Jul 2024)
Tucumán, Argentina
- Designed and implemented a multi-jurisdictional tax calculation engine in Java/Spring Boot for POS environments across complex cross-border rule sets
- Rebuilt critical batch processing pipelines across Java microservices, improving API response times under high concurrency (from ~1s to ~100ms average)
- Standardized CI/CD workflows across engineering teams using Azure DevOps and Jenkins

### Java Software Designer – JP Morgan Chase - Globant / Sistemas Globales S.A. (Mar 2022 - Jul 2022)
Tucumán, Argentina
- Embedded in a JP Morgan Chase engineering team; remediated security vulnerabilities flagged by Veracode and improved Maven dependency management
- Performed testing, packaging, and deployment of Spring Boot microservices in a regulated banking environment

### Software Engineer - Mercado Libre / MercadoLibre S.R.L. (Sep 2021 - Mar 2022)
Remote, Argentina
- Built a Go REST API to ingest and process daily Visa offline transaction CSV files, computing financial impact and feeding downstream reconciliation workflows
- Designed and ran automated stress-testing pipelines with Artillery (internal "Bazoka" suite), using Datadog (primary) and New Relic (select metrics) to monitor peak load and failures; validated production auto-scaling under high transaction volume
- Developed a Go REST API to onboard and classify MercadoPago sellers (large, medium, small), persisting fiscal entity data in DynamoDB (CUIL → legal name) and applying segment-specific tax rules

### Software Engineer / Tech Lead - Sovos / Sovos Compliance SA (Feb 2016 - Aug 2021)
Tucumán, Argentina
- Led cross-functional teams of 4–6 engineers, driving technical decisions, mentoring, and improving delivery predictability
- Architected and built event-driven tax-calculation microservices using Java/Spring Boot and RabbitMQ
- Led a Snowflake–Kafka proof of concept for real-time data integration, improving processing throughput by ~50% in testing
- Established CI/CD pipelines with Jenkins across multiple teams; designed POS frontend components with AngularJS (legacy) and Java 8

### Java Developer / Application Support - Hewlett-Packard (Apr 2014 - Feb 2016)
Córdoba, Argentina (also supported DFW-TX operations)
- Developed and maintained SOAP/REST web services for American Airlines reservation systems
- Provided 24/7 on-call production and UAT support under strict global SLA obligations

### Java Software Developer - Globant / Sistemas Globales S.A. (May 2013 - Apr 2014)
Yerba Buena, Tucumán, Argentina
- Built an internal travel portal from scratch (Java 7, Spring 3, Hibernate/JPA, Thymeleaf/jQuery)

### Earlier Experience (2008–2013)
- Full Stack Developer at HITMedia / La Gaceta (Jul 2012 – May 2013) — lagaceta.com.ar (PHP, CodeIgniter, MySQL, Memcached, Apache Solr)
- Software Developer at Everis / NTT Data (2010–2012) — Java, Flex, Struts, Spring, Hibernate, PL/SQL (incl. Movistar Argentina)
- Java Software Developer at Hewlett-Packard (Jul 2011 – Oct/Nov 2011) — Java 6, SOAP web services
- Developer at Citytech (Sep 2008 – Apr 2010)

## Independent Projects
- None listed on CV

## Technical Skills

### Programming & Backend
- **Java** (expert): Spring Boot, Spring MVC, Hibernate/JPA, Java 8/11/17, microservices, DDD, SOLID
- **Node.js/TypeScript** (working): NestJS, TypeORM, clean architecture
- **Go** (working): REST APIs at MercadoPago (Visa offline reconciliation, seller onboarding)
- **JavaScript/TypeScript**: React, AngularJS (legacy)
- **SQL & Shell**: MySQL, PostgreSQL, SQL Server, Oracle, Snowflake, DynamoDB

### Messaging & Integration
- Kafka, RabbitMQ

### Observability & Testing
- Datadog, New Relic, Artillery, JUnit, Mockito, integration testing

### DevOps & Practices
- Docker, Jenkins, Azure DevOps, Git, Maven, Gradle
- CI/CD, microservices, REST APIs, Agile/Scrum
- Veracode (static analysis remediation)

### Domain Expertise
- Tax compliance and regulatory technology (POS integrations)
- Fintech and acquirer operations (MercadoPago: Visa offline reconciliation, seller fiscal onboarding)
- Banking and regulated environments (JP Morgan Chase)
- Logistics and shipment traceability (Correo Argentino)
- Airline reservation systems (American Airlines support background)

### Software & Tools
- MySQL, PostgreSQL, SQL Server, Oracle, Snowflake, DynamoDB, Docker, Jenkins, Azure DevOps, Git, Maven, Gradle, Datadog, New Relic, Artillery, Veracode

## Publications
- None

## Awards
- None listed

## Certifications
- Oracle Certified Associate, Java SE 7 Programmer (1Z0-803) — 2014

## References
- Available upon request

## Source notes
- Employment dates aligned to `documents/references/historial-laboral.txt` (AFIP-style razón social mapping to known brands).
- Achievement metrics prefer the richer, interview-defendable claims from LinkedIn / `Martin_Grellet.pdf` when they do not conflict with the historial.
- **Mercado Libre detail (interview):** Visa offline CSV ingestion API tracked financial impact and handed off to downstream reconciliation/settlement workflows (user did not own COELSA or paying-bank settlement directly). Seller API classified merchants by size with DynamoDB-backed CUIL lookup and segment tax rules. Stress testing used internal Artillery suite nicknamed "Bazoka"; Datadog was the primary observability tool, with New Relic used for certain production metrics.
