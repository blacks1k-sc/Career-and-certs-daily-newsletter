# TECH CAREER ROADMAP
**Cloud (AWS-First) DevOps Cybersecurity AI-Era Security Offensive Security**

A compressed 4-month sprint for a CS new grad targeting Toronto tech roles in Q1 2027.

AWS CCP + SAA + Security+ + portfolio project + AI security skills + job search all by September 1. This is an aggressive timeline.

**30+ hours/week minimum. No days off from the plan.**

| | |
|---|---|
| **Timeline** | May 1-September 1, 2026 (4 months/17 weeks) |
| **Cloud Platform** | AWS (primary) + Azure (secondary exposure) |
| **Study Load** | 30-35 hours/week minimum (non-negotiable at this pace) |
| **Version** | v3.0-Compressed Sprint |
| **Generated** | April 30, 2026 |

### WHAT CHANGED FROM v2 (8-month plan):
* CCP compressed to 10 days (it's easy for CS students).
* SAA compressed to 5 weeks.
* Security+ compressed to 4 weeks.
* Phase 5 tracks (AppSec, SOC, GRC, AI Security) run CONCURRENTLY with portfolio build to save 3 weeks.
* Offensive security moved entirely post-Sep 1 (Tier 3 do it while employed).
* Job search prep is the final week, with full-intensity applications starting Sep 1. This works only if you do 30+ hrs/week.

### TARGETING STRATEGY

| Tier | Roles | Strategy |
|---|---|---|
| **TIER 1** | Jr DevOps/Platform/Cloud/Infra Engineer, GRC/IT Risk Analyst | Apply aggressively starting Sep 1. Banks + consulting = primary. |
| **TIER 2** | SOC Analyst (MSSP), Cloud Support, Jr Security Consultant | Apply in parallel. SOC = stepping stone (12-18 mo max). |
| **TIER 3** | Pentester / Red Team / AI Security Researcher | Build CTF skills AFTER Sep 1 while employed in Tier 1/2. |

### 17-WEEK COMPRESSED TIMELINE

| Period | Weeks | Focus | Deliverable |
|---|---|---|---|
| May 1-11 | 1.5 | Cloud Foundations + AWS CCP | AWS CCP Cert |
| May 12-Jun 15 | 5 | AWS SAA Deep Dive | AWS SAA Cert |
| Jun 16-Jul 12 | 4 | Security+ (accelerated) | CompTIA Security+ Cert |
| Jul 14-Aug 3 | 3 | Portfolio Project + AI Sec + AppSec + SOC + GRC (concurrent) | ParcelVision on AWS + security skills + write-ups |
| Aug 4-24 | 3 | AI Security + remaining skills + Azure exposure | AI security write-ups + AZ-900 study + GRC frameworks |
| Aug 25-Sep 1 | 1 | Job search launch prep | 3 resumes + LinkedIn + portfolio + first 15 applications |

---

## PHASE 1 — AWS CLOUD PRACTITIONER (CLF-C02)
**May 1 - May 11, 2026 | 10 Days**

**Goal:** Pass CCP in 10 days. This is aggressive but realistic for a CS student - CCP is fundamentally a vocabulary exam. You already understand computing concepts; you just need to learn AWS-specific names and pricing models. 4-5 hours/day.

**Days 1-4: Core Services + Infrastructure (May 1 - May 4)**
- [ ] Cloud models (IaaS/PaaS/SaaS), deployment models (public/private/hybrid) May 1
- [ ] AWS global infra: Regions, AZs, Edge Locations, Local Zones May 1
- [ ] Compute: EC2 (instance families, pricing: On-Demand/Reserved/Spot), Lambda, ECS/EKS May 2
- [ ] Storage: S3 (classes, lifecycle), EBS, EFS — when to use each May 3
- [ ] Networking: VPC basics, subnets, IGW, NAT, Route 53, CloudFront May 3
- [ ] Databases: RDS, Aurora, DynamoDB, Redshift - relational vs NoSQL decisions May 4

**Days 5-7: Security + IAM + Billing (May 5 - May 7)**
- [ ] IAM: Users, Groups, Roles, Policies, least privilege, MFA May 5
- [ ] Shared Responsibility Model - what AWS secures vs what YOU secure May 5
- [ ] Security services: GuardDuty, Inspector, Macie, WAF, Shield, KMS, CloudTrail, Config May 6
- [ ] Billing: Free Tier, Cost Explorer, Budgets, Trusted Advisor, Organizations, Support plans May 7
- [ ] Set up AWS free tier account - launch EC2, create S3 bucket, create IAM user May 7

**Days 8-10: Practice Exams + Pass (May 8 - May 11)**
- [ ] Complete 3 full Tutorials Dojo CCP practice exams May 9
- [ ] Review every wrong answer. Flashcards for confused services. May 10
- [ ] **BOOK AND PASS AWS CCP EXAM (CLF-C02)** May 11

**DEADLINE:** May 11 — AWS CCP PASSED. Non-negotiable.

### RESOURCES
* **Andrew Brown (ExamPro) CCP Course:** Free on YouTube (~14h). Best free CCP course. Watch at 1.5x speed.
* **Tutorials Dojo CCP Practice Exams:** $12. Gold standard. Do every single one.
* **Tech With Lucy (YouTube):** Canadian cloud engineer. CCP breakdowns + career advice.

---

## PHASE 2 — AWS SOLUTIONS ARCHITECT ASSOCIATE (SAA-C03)
**May 12 - June 15, 2026 | 5 Weeks**

**Goal:** Pass SAA in 5 weeks (compressed from 7). Possible because CCP gave you the vocabulary. Now you go deep on architecture. 5-6 hours/day. Adrian Cantrill's course is non-negotiable — do NOT substitute with a cheaper/shorter course.

**Weeks 1-2: IAM + Compute + Networking (May 12 - May 25)**
- [ ] Cantrill SAA: IAM deep dive (policy evaluation, cross-account, permission boundaries) May 15
- [ ] EC2 deep dive (placement groups, ENIs, EBS vs instance store, AMIs) May 18
- [ ] VPC deep dive (NACLs vs SGs, peering, endpoints, Transit Gateway, Flow Logs) May 22
- [ ] Lab: Multi-tier VPC by hand — public web + private DB + NAT + bastion May 25

**DEADLINE:** May 25 — IAM + EC2 + VPC complete. Lab deployed.

**Week 3: Storage + Databases + Serverless (May 26 - Jun 1)**
- [ ] S3 deep dive (encryption, replication, access points, presigned URLs) May 28
- [ ] RDS (Multi-AZ, read replicas), Aurora, DynamoDB (partition keys, GSI/LSI) May 29
- [ ] Lambda, API Gateway, Step Functions, SQS, SNS, ECS/Fargate, ECR May 31
- [ ] Lab: Serverless API (Lambda + API Gateway + DynamoDB) Jun 1

**DEADLINE:** June 1 — Storage, DB, serverless, containers complete.

**Week 4: Advanced + Security + HA/DR (Jun 2 - Jun 8)**
- [ ] CloudFront, Route 53, ELB/ALB/NLB, Auto Scaling, Global Accelerator Jun 4
- [ ] CloudWatch, CloudTrail, Config, GuardDuty, Security Hub, KMS, ACM Jun 5
- [ ] HA patterns: Multi-AZ, multi-Region, pilot light, warm standby Jun 7
- [ ] Migration: Snow Family, Storage Gateway, DMS. Cost optimization. Jun 8

**DEADLINE:** June 8 - All SAA course modules complete.

**Week 5: Exam Prep + Pass (Jun 9 - Jun 15)**
- [ ] ALL Tutorials Dojo SAA practice exams (4 minimum) Jun 12
- [ ] Review every wrong answer. Score 82%+ consistently. Jun 14
- [ ] **BOOK AND PASS AWS SAA EXAM (SAA-C03)** Jun 15

**DEADLINE:** June 15 - AWS SAA PASSED. Non-negotiable. You now have 2 AWS certs.

### RESOURCES
* **Adrian Cantrill SAA Course:** learn.cantrill.io — $45 USD. Non-negotiable. Best SAA course.
* **Tutorials Dojo SAA Practice Exams:** Gold standard. Buy the set.
* **Johnny Chivers (YouTube):** Deep AWS architecture. Networking + security focus.
* **Cloud Mechanic (YouTube):** Short, dense service-specific videos.
* **Be A Better Dev (YouTube):** AWS with code examples and real deployments.

---

## PHASE 3 — COMPTIA SECURITY+ SY0-701 (ACCELERATED)
**June 16 - July 12, 2026 | 4 Weeks**

**Goal:** Pass Security+ in 4 weeks (compressed from 6). Aggressive but achievable — you have a CS foundation and just learned cloud security concepts in SAA. Professor Messer at 1.5x speed + heavy practice exams. 5 hours/day.

**Week 1: Domains 1-2 (Jun 16 - Jun 22)**
- [ ] Domain 1: General Security Concepts (CIA triad, AAA, zero trust, defense in depth) Jun 18
- [ ] Domain 2: Threats, Vulnerabilities, Mitigations (malware, social eng, attack vectors) Jun 22
- [ ] Set up home lab: VirtualBox + Kali Linux + Metasploitable3 Jun 22

**Week 2: Domains 3-4 (Jun 23 - Jun 29)**
- [ ] Domain 3: Security Architecture (segmentation, cloud models, encryption, PKI) Jun 26
- [ ] Domain 4: Security Operations (monitoring, IR lifecycle, SIEM, SOAR) Jun 29
- [ ] Lab: Install Splunk Free. Ingest logs. Write 5 SPL queries. Jun 29

**Week 3: Domain 5 + Practice (Jun 30 - Jul 6)**
- [ ] Domain 5: Security Program Management (GRC, compliance, risk, audits) Jul 2
- [ ] ALL Professor Messer practice exams (3 minimum) Jul 5
- [ ] Jason Dion practice exams as supplement Jul 6

**Week 4: Final Prep + Pass (Jul 7 - Jul 12)**
- [ ] Review PBQ formats: drag-drop, log analysis, config scenarios Jul 8
- [ ] Score 82%+ consistently on all practice tests Jul 10
- [ ] **BOOK AND PASS COMPTIA SECURITY+ SY0-701** Jul 12

**DEADLINE:** July 12 — SECURITY+ PASSED. Non-negotiable. 3 certs in hand.

### RESOURCES
* **Professor Messer SY0-701:** Free on YouTube. Buy practice exams ($30).
* **Jason Dion Practice Exams:** Udemy. Harder than real exam.
* **Cyberkraft (YouTube):** Better than Messer on cryptography.
* **John Hammond (YouTube):** Malware analysis + CTF walkthroughs. Watch 2-3/week.
* **MyDFIR (YouTube):** SOC analyst projects. Replicate his lab builds.
* **TryHackMe SOC Level 1 path:** Start during this phase, finish in Phase 4.

---

## PHASE 4 — PARCELVISION BUILD + CONCURRENT SECURITY SKILLS
**July 14 - August 3, 2026 | 3 Weeks**

**Goal:** Deploy ParcelVision on AWS AND build AppSec/SOC/GRC skills SIMULTANEOUSLY. Morning = project build. Evening = PortSwigger/Splunk/GRC study. This is the highest-intensity phase. 6-7 hours/day, split across both tracks.

### TRACK A: PARCELVISION DEPLOYMENT (mornings, 3-4 hrs/day)

**Week 1: Terraform + Containers + CI/CD (Jul 14 - Jul 20)**
- [ ] All AWS infra in Terraform (VPC, subnets, SGs, ECS, RDS, S3) Jul 16
- [ ] IAM roles per service (no access keys, use task roles) Jul 16
- [ ] Remote state: S3 backend + DynamoDB locking Jul 17
- [ ] Dockerize Flask app (multi-stage build) → push to ECR Jul 18
- [ ] GitHub Actions pipeline: lint → test → build → scan → deploy Jul 19
- [ ] Trivy (container scan) + Semgrep (SAST) + Checkov (IaC scan) integrated Jul 20

**Week 2: Security Hardening (Jul 21 - Jul 27)**
- [ ] Encryption: S3 SSE-KMS, RDS encryption, EBS encryption, ACM certs, TLS 1.2+ Jul 23
- [ ] CloudTrail + GuardDuty + AWS Config rules + VPC Flow Logs Jul 25
- [ ] Security Hub enabled — achieve passing score Jul 26
- [ ] Secrets Manager for API keys (Gemini API, etc.) Jul 27

**Week 3: Monitoring + Docs (Jul 28 - Aug 3)**
- [ ] CloudWatch dashboards + alerting (unauthorized calls, SG changes, errors) Jul 30
- [ ] Architecture diagram (draw.io) + Security Decisions document Aug 1
- [ ] Comprehensive README + 3-5 min demo walkthrough video Aug 3

**DEADLINE:** August 3 - ParcelVision LIVE on AWS. Terraform, CI/CD, security scanning, monitoring, full docs.

### TRACK B: APPSEC + SOC + GRC (evenings, 2-3 hrs/day, concurrent with Track A)

**AppSec**
- [ ] PortSwigger Labs (Jul 14 - Aug 3)
- [ ] SQL Injection labs (Apprentice + Practitioner) Jul 17
- [ ] XSS labs complete Jul 20
- [ ] Authentication + Access Control labs Jul 24
- [ ] SSRF + Path Traversal + File Upload labs Jul 27
- [ ] Burp Suite Community Edition used for every lab Jul 14
- [ ] 3 professional vulnerability write-ups (finding → impact → fix → PoC) Aug 3

**SOC Skills (Jul 14 - Aug 3)**
- [ ] Complete TryHackMe SOC Level 1 path (started in Phase 3) Jul 24
- [ ] Splunk Fundamentals 1 complete Jul 27
- [ ] BOTS v1 dataset investigation done Aug 1
- [ ] MITRE ATT&CK: tactics, techniques, detection mapping understood Aug 3

**GRC Foundations (Jul 14 - Aug 3)**
- [ ] SOC 2 Type II: 5 Trust Service Criteria Jul 18
- [ ] ISO 27001 structure + NIST CSF 5 functions Jul 22
- [ ] OSFI B-13 guidelines (Canadian bank requirement) Jul 26
- [ ] PIPEDA basics + Quebec Law 25 awareness Jul 30
- [ ] Write sample risk assessment + Acceptable Use Policy Aug 3

---

## PHASE 5 — AI-ERA SECURITY + REMAINING SKILLS + AZURE EXPOSURE
**August 4 - August 24, 2026 | 3 Weeks**

**Goal:** This is your differentiation phase. AI security knowledge separates you from every other 2027 grad. Also: finish remaining AppSec write-ups, study OWASP Top 10, add Azure exposure, study AI governance frameworks. This is what makes you interview-ready.

**AI-ERA SECURITY - NEW ATTACK SURFACE**
Why this matters: Every company deploying AI creates vulnerabilities that traditional security doesn't cover. Almost no entry-level candidates know OWASP LLM Top 10 or MITRE ATLAS. This is your edge.

**Week 1: Understanding AI/ML Threats (Aug 4 - Aug 10)**
- [ ] OWASP Top 10 for LLM Applications (2025) — read cover to cover Aug 5
- [ ] Prompt Injection: direct, indirect, jailbreaking - practice on vulnerable LLM apps Aug 6
- [ ] Data Poisoning, Model Theft/Extraction, Supply Chain attacks on ML pipelines Aug 7
- [ ] Insecure Output Handling: XSS via LLM, SQL injection via LLM Aug 8
- [ ] Excessive Agency: when AI agents get manipulated into harmful actions Aug 9
- [ ] Study real incidents: Samsung ChatGPT leak, Air Canada chatbot case, Microsoft Tay Aug 10

**Week 2: Defending AI Systems + AI-Powered Attacks (Aug 11 - Aug 17)**
- [ ] MITRE ATLAS (Adversarial Threat Landscape for AI Systems) - ATT&CK for AI Aug 12
- [ ] Guardrails: input validation for LLMs, output filtering, sandboxing agent actions Aug 13
- [ ] How attackers USE AI: AI-gen phishing, deepfakes, automated vuln discovery Aug 14
- [ ] Lab: Exploit vulnerable LLM app (OWASP WebGoat AI or Damn Vulnerable LLM App) Aug 15
- [ ] Lab: Implement guardrails on LLM API (input sanitization, rate limiting, logging) Aug 16
- [ ] AI-augmented SOC: how CrowdStrike Charlotte AI, Microsoft Copilot for Security work Aug 17

**Week 3: Write-ups + Azure + AI Governance + OWASP Top 10 (Aug 18 - Aug 24)**
- [ ] Write 2 AI security blog posts: LLM prompt injection (with PoC) + securing AI in AWS Aug 20
- [ ] Complete remaining 2 AppSec write-ups (total = 5 AppSec + 2 AI = 7 write-ups) Aug 21
- [ ] Study OWASP Top 10 (2021) - explain each, give examples, describe fixes Aug 21
- [ ] Study OAuth 2.0 + JWT security flaws Aug 22
- [ ] NIST AI Risk Management Framework + EU AI Act awareness Aug 22
- [ ] Write sample AI Usage Policy for an organization Aug 23
- [ ] AZ-900 study: Microsoft Learn path (~8 hrs free). Optionally sit exam ($125). Aug 24
- [ ] Azure labs: deploy basic App Service + understand Entra ID, Defender, Sentinel basics Aug 24
- [ ] Add AI security section to ParcelVision: threat model for Gemini API integration Aug 24

**DEADLINE:** August 24 — AI security knowledge complete. 7 write-ups published. Azure exposure done. OWASP/GRC interview-ready.

### AI SECURITY RESOURCES
* **OWASP Top 10 for LLM Applications:** owasp.org - THE reference. Read cover to cover.
* **MITRE ATLAS:** atlas.mitre.org - Study like ATT&CK.
* **Embrace The Red (Johann Rehberger):** Leading indirect prompt injection researcher.
* **Joseph Thacker / rez0 (YouTube):** AI/LLM bug bounty. Real exploits.
* **DEF CON AI Village talks:** YouTube. Cutting-edge AI security research.
* **Trail of Bits AI Security Blog:** Deep technical ML/AI vulnerability analysis.
* **PortSwigger Web Security Academy:** portswigger.net/web-security - Best AppSec training.
* **Rana Khalil (YouTube):** PortSwigger walkthroughs. Logic, not just steps.
* **PwnFunction (YouTube):** Animated web vuln explanations.

---

## PHASE 6 — JOB SEARCH LAUNCH
**August 25 - September 1, 2026 | 1 Week Launch (then ongoing)**

**Goal:** By Sep 1 you have 3 certs (CCP+SAA+Security+), a live cloud project, 7 security write-ups, AI security knowledge, and Azure exposure. This week you package it all and start applying. 15+ targeted apps/week from Sep 1 onward.

**Launch Week (Aug 25 - Sep 1)**
- [ ] Create master resume with all projects, 3 certs, and skills Aug 26
- [ ] 3 tailored variants: Cloud/DevOps, GRC/Security, SOC/SecOps Aug 27
- [ ] LinkedIn headline: 'AWS SAA | Security+ | Cloud Security | DevOps | AI Security' Aug 27
- [ ] Portfolio page/README: ParcelVision + security write-ups + AI security labs Aug 28
- [ ] 'Tell me about yourself' pitch for each role type (practice out loud 5x each) Aug 29
- [ ] Set LinkedIn job alerts for all target role titles + Toronto Aug 29
- [ ] Submit first 15 targeted applications Sep 1

**DEADLINE:** September 1 — Job search LIVE. Everything done. All preparation complete.

### Application Targets:

| Type | Companies | Roles |
|---|---|---|
| **Banks** | RBC, TD, BMO, Scotiabank, CIBC | IT Risk Analyst, GRC Analyst, Cloud Engineer, Technology Risk, Info Security Analyst |
| **Consulting** | Deloitte, EY, KPMG, PwC, CGI, Accenture | Jr Security Consultant, Cloud Consultant, Risk Advisory, Tech Consulting |
| **MSSPs** | Arctic Wolf, eSentire, GoSecure, Cyderes, CrowdStrike | SOC Analyst, Security Analyst, Threat Analyst, Detection Engineer |
| **Tech/Gov** | AWS, Shopify, Wealthsimple, 1Password, CSE/CCCS, Shared Services, Ontario PS | Cloud Support, DevOps, SRE, Platform Engineer, Infra Engineer, IT Security Analyst, Cloud Ops, Systems Admin |

**Job Boards:**
* **LinkedIn Jobs:** Primary. Alerts for all role titles + Toronto.
* **Indeed Canada + Company career pages:** Banks/Big 4 post on own portals first.
* **GCJobs (jobs.gc.ca):** Government. Slow but stable.
* **YorkU Career Hub:** University connections matter.

**Networking (start during Phase 4, continue post Sep 1):**
- [ ] BSides Toronto / SecTor — attend when scheduled
- [ ] OWASP Toronto Chapter - monthly meetups
- [ ] Toronto AWS User Group - monthly meetups
- [ ] ISACA Toronto Chapter — GRC focused, bank connections

**POST SEP 1 OFFENSIVE SECURITY (background, while job searching):**
OffSec is Tier 3. Do NOT spend time on this before Sep 1. Once job search is active, spend 1-2 hrs/day on CTFs as skill building. Target OSCP only after you're employed.
- [ ] HackTheBox Starting Point + 10 Easy machines
- [ ] TryHackMe Jr Penetration Tester path
- [ ] Blog write-ups for every machine (methodology, not just flags)
- [ ] Evaluate OSCP purchase once employed
- **IppSec (YouTube):** Gold standard HTB walkthroughs.
- **TCM Security (Heath Adams):** Best affordable pentesting course ($30/mo).
- **Conda / Alh4zr3d / John Hammond (YouTube):** Practical offsec content.

---

## CERTIFICATION SEQUENCE

| # | Certification | Deadline | Cost (CAD) | Why |
|---|---|---|---|---|
| 1 | AWS Cloud Practitioner | May 11 | ~$140 | Cloud vocabulary foundation. Gateway to SAA. |
| 2 | AWS Solutions Architect Assoc | Jun 15 | ~$260 | Primary cloud credential. 3,000+ Toronto jobs. Global portability. |
| 3 | CompTIA Security+ SY0-701 | Jul 12 | ~$500 | Universal security entry ticket. Banks/SOC/GRC all filter on it. |
| 4 | AZ-900 (optional) | Aug 24 | ~$125 | Multi-cloud signal. Easy win if time allows. |
| 5 | AWS Security Specialty | Post-hire | ~$200 | Cloud security differentiator. Study once employed. |
| 6 | OSCP | 2027-28 | ~$2,200 USD | OffSec gold standard. Only after 12+ months employed. |

---

## COST BREAKDOWN

| Item | CAD | Required? |
|---|---|---|
| AWS CCP Exam | ~$140 | Yes |
| Cantrill SAA Course | ~$60 | Yes |
| AWS SAA Exam | ~$200 | Yes |
| Tutorials Dojo (CCP+SAA) | ~$25 | Yes |
| Security+ Exam | ~$500 | Yes |
| Messer Practice Exams | ~$40 | Yes |
| AZ-900 Exam | ~$125 | Recommended |
| AWS Free Tier overages | ~$30 | Budget for it |
| **TOTAL (Essential)** | **~$995** | |
| **TOTAL (Everything)** | **~$1,120** | |

---

## NON-NEGOTIABLE RULES
1. **30+ hours/week.** This compressed timeline does NOT work at 15 hrs/week. Be honest with yourself.
2. **One cert at a time.** CCP → SAA → Security+. Never parallel cert study.
3. **Do NOT skip labs.** A cert without hands-on is a piece of paper. The labs are the learning.
4. **Phase 4 is the hardest phase.** project + 3 concurrent skill tracks. Plan your days hour by hour.
5. **Offensive security is POST Sep 1 only.** Do not touch CTFs before your certs and project are done.
6. **AI security is your EDGE.** Most 2027 grads won't know OWASP LLM Top 10. You will. Lean into it.
7. **AWS first, Azure second.** AZ-900 is a nice-to-have. SAA is the must-have.
8. **Your ParcelVision project + write-ups matter more than a 4th certification.**
9. **Apply broadly from Sep 1:** banks, MSSPs, consulting. Get employed. Specialize later.
10. **If you fall behind, cut AZ-900 and OffSec first.** Never cut certs or the project.

---

## MASTER MILESTONE CHECKLIST
- [ ] [May 11] AWS Cloud Practitioner (CLF-C02) — PASSED
- [ ] [Jun 15] AWS Solutions Architect Associate (SAA-C03) - PASSED
- [ ] [Jul 12] CompTIA Security+ SY0-701 - PASSED
- [ ] [Aug 3] ParcelVision Cloud Redeployment - LIVE on AWS with full documentation
- [ ] [Aug 3] PortSwigger Academy Core lab categories complete (SQLI, XSS, Auth, Access Control, SSRF)
- [ ] [Aug 3] Splunk Fundamentals 1 + BOTS v1 investigation - Complete
- [ ] [Aug 3] TryHackMe SOC Level 1 path — Complete
- [ ] [Aug 3] GRC frameworks (SOC 2, ISO 27001, NIST CSF, OSFI B-13, PIPEDA) - Interview ready
- [ ] [Aug 3] 3 AppSec vulnerability write-ups — Published
- [ ] [Aug 17] OWASP LLM Top 10 + MITRE ATLAS - Can explain in interview
- [ ] [Aug 17] Vulnerable LLM app exploited + guardrails implemented (labs complete)
- [ ] [Aug 24] 2 AI security blog posts — Published (total = 5 AppSec + 2 AI = 7 write-ups)
- [ ] [Aug 24] Remaining 2 AppSec write-ups complete (total = 5)
- [ ] [Aug 24] OWASP Top 10 (2021) + OAuth/JWT security — Can explain in interview
- [ ] [Aug 24] NIST AI RMF + EU AI Act - Awareness level for GRC interviews
- [ ] [Aug 24] AZ-900 Azure Fundamentals — Studied (exam optional)
- [ ] [Aug 24] AI security section added to ParcelVision (Gemini API threat model)
- [ ] [Aug 28] 3 resume variants + LinkedIn + portfolio page — Complete
- [ ] [Sep 1] First 15 targeted job applications - Submitted
- [ ] [Sep 1] ALL PREPARATION COMPLETE. Job search is now full-time alongside school/work.
- [ ] [Q1 2027] EMPLOYED in a Tier 1 or Tier 2 role

> 4 months. 3 certs. 1 production project. 7 security write-ups. AI-era security knowledge. Multi-cloud exposure.
> 
> This is a sprint, not a marathon. The pace is brutal but the payoff is real: by September 1 you'll have more demonstrable skills than 90% of 2027 CS grads applying for the same roles.
> 
> The goal hasn't changed: get inside the ecosystem. Get hired. Then specialize from the inside. Every day you delay starting is a day closer to graduation without preparation.
> 
> **Start May 1. No excuses.**
