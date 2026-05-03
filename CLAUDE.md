# Claude Project Instructions — Daily Career Roadmap Newsletter

## Project Purpose

This repository powers an automated daily career roadmap newsletter.

The goal is to generate highly informative daily certification-study newsletters based on the scheduled roadmap topic for the current date. Each newsletter should help Shaurya prepare for cloud, DevOps, cybersecurity, GRC, SOC, AppSec, AI-security, and related technical roles.

The newsletter must help Shaurya:

1. Ace the relevant certification exams.
2. Become job-ready for cloud, DevOps, cybersecurity, GRC, SOC, AppSec, AI-security, and related technical roles.
3. Build interview-ready knowledge, not just memorize definitions.
4. Understand how each topic appears in real companies, cloud environments, banking/finance teams, SOC teams, DevOps teams, security programs, and portfolio projects.
## Repository File Structure

Use this repository structure:

```text
career-certs-daily-newsletters/
  CLAUDE.md

  context/
    career_roadmap_context/
      career_roadmap_v3_sprint.md
      career_roadmap_v3_sprint.pdf
```

## Newsletter Generation 

Generate today’s career roadmap newsletter using the Career Roadmap Newsletter project knowledge, the uploaded roadmap PDF
Use the uploaded roadmap as the source of truth for all newsletter generation. The goal is to generate highly informative daily certification-study newsletters based only on the scheduled roadmap topic for the requested date.

Since May 1, May 2, and May 3 were already tested manually, begin automated daily generation from May 4 onward. If today’s date is May 4 or later, use today’s scheduled topic. If there is no exact date match, use the nearest upcoming topic and clearly state that it is the nearest upcoming topic.

The end goal is to help me:
1. Ace the relevant certification exams.
2. Become job-ready for cloud, DevOps, cybersecurity, GRC, SOC, AppSec, AI-security, and related technical roles.
3. Build interview-ready knowledge, not just memorize definitions.
4. Understand how each topic appears in real companies, cloud environments, banking/finance teams, SOC teams, DevOps teams, security programs, and portfolio projects.


Only generate content for the roadmap topic scheduled for that date. Do not include future phases or unrelated categories unless the scheduled topic belongs to that phase. If multiple topics are scheduled for the same date, combine them into one focused newsletter for that date. If there is no exact date match, use the nearest upcoming topic and clearly state that it is the nearest upcoming topic.

## Depth and Upskilling Rules

Each newsletter must be written to genuinely improve Shaurya’s technical skill, not just summarize the roadmap item.

For every scheduled topic, the newsletter must include enough depth to help Shaurya become stronger in certification exams, technical interviews, real workplace reasoning, and portfolio project explanation.

The newsletter should teach the topic at three levels:

1. Exam level — what the certification expects Shaurya to know.
2. Real-world level — how the concept is used in actual cloud, security, DevOps, SOC, GRC, AppSec, AI-security, or banking environments.
3. Interview level — how Shaurya should explain the concept clearly, confidently, and with examples.

For every technical topic, include:

- Why the topic matters.
- What problem it solves.
- How it works internally or conceptually.
- When to use it.
- When not to use it.
- Common tradeoffs.
- Common beginner mistakes.
- How it connects to job responsibilities.
- How it could appear in a certification exam.
- How it could appear in a technical or behavioral interview.

Prioritize practical mental models over shallow definitions.

Use examples wherever useful, especially examples involving:

- Cloud architecture decisions.
- Security risk decisions.
- DevOps deployment decisions.
- Monitoring and incident response decisions.
- Banking, consulting, MSSP, or enterprise technology environments.
- Portfolio project explanations.

The newsletter must not be motivational-only. It must contain dense, useful technical learning.

Avoid generic advice such as “study hard,” “review documentation,” or “understand the basics” unless it is paired with specific action.

When explaining a concept, make Shaurya better at answering:

- What is it?
- Why does it exist?
- What problem does it solve?
- How does it work?
- What are the tradeoffs?
- What would I choose in a real company?
- What would I say in an interview?
- What mistake would a beginner make?
- What would an exam question try to trick me on?

Each newsletter should include at least one “senior engineer insight” or “real-world judgment” point that goes beyond basic certification memorization.

The newsletter should make Shaurya more fluent in professional technical language while still being clear and understandable.

The goal is not just to pass exams. The goal is to build job-ready technical judgment.

Before sending the newsletter, verify important factual claims wherever possible using reliable sources. Prioritize official and reputable sources:
- AWS official documentation for AWS services, infrastructure, IAM, VPC, S3, EC2, Lambda, CloudFront, Route 53, Well-Architected Framework, security services, pricing models, and certification-related facts.
- CompTIA official exam objectives and reputable Security+ sources for Security+ topics.
- OWASP official resources for AppSec and LLM security.
- MITRE ATT&CK and MITRE ATLAS for SOC, detection, adversary behavior, and AI-security threats.
- NIST, ISO, SOC 2, OSFI, and official Canadian privacy/compliance sources for GRC topics.
- Microsoft Learn for Azure topics.

Do not invent exact statistics, service counts, pricing numbers, region counts, edge-location counts, laws, certification details, or current service capabilities. If a fact may change over time and cannot be verified, avoid exact numbers and use general wording. If verification is not possible, clearly say that the fact should be verified from the official source before relying on it.

Before the newsletter body begins, include one original intense motivational quote. The quote must appear at the very beginning of the email body, before the date/title. It must be written for a 22-year-old who tends to procrastinate, delay important work, and leave things for later. The quote must be different every day. It should be direct, serious, and mentally challenging, not cheesy. It should focus on laziness, urgency, discipline, consistency, identity change, delayed gratification, and the cost of wasting time. For most days, especially 3–7 days per week, make the quote target procrastination and laziness directly. For the remaining days, make the quote focus on ambition, confidence, resilience, focus, long-term success, or becoming the kind of person who follows through. Do not quote famous people unless explicitly asked. Generate an original quote instead. Keep the quote short: 1–3 sentences maximum.

Each newsletter must include:
1. Motivational quote at the very beginning of the email body
2. Date and roadmap topic
3. Certification target
4. What I must be able to explain or do after studying this topic
5. Deep fundamentals explained clearly, with enough detail to make me more knowledgeable after reading
6. Real-world practical relevance: how this topic is used in companies, cloud systems, banks, SOC teams, DevOps teams, security programs, or technical interviews
7. Interview angle: how this topic could appear in an interview and what a strong candidate should say
8. Common exam traps and misconceptions
9. Must-know terms formatted as: Term — definition
10. Three to five free study resources, prioritizing official documentation and reputable free learning material
11. One 30–60 minute hands-on task
12. Five certification-style multiple-choice questions
13. Answer key with short explanations, including why wrong answers are wrong when useful
14. Three-item checklist for the day

Question rules:
- If the scheduled topic is AWS CCP, create vocabulary, service-purpose, shared-responsibility, billing, infrastructure, cloud-concept, and basic security questions.
- If the scheduled topic is AWS SAA, create scenario-based architecture questions about reliability, security, networking, storage, compute, cost, high availability, disaster recovery, and tradeoffs.
- If the scheduled topic is Security+, create questions about threats, controls, incident response, governance, risk, compliance, identity, cryptography, network security, and security operations.
- If the scheduled topic is AppSec, create questions about OWASP Top 10, authentication, access control, SQL injection, XSS, SSRF, file upload, secure coding, vulnerability impact, and remediation.
- If the scheduled topic is SOC, create questions about SIEM, log analysis, alerts, MITRE ATT&CK, incident response, detection logic, false positives, and triage.
- If the scheduled topic is GRC, create questions about SOC 2, ISO 27001, NIST CSF, OSFI B-13, PIPEDA, risk, controls, audits, evidence, policies, and third-party risk.
- If the scheduled topic is AI Security, create questions about OWASP LLM Top 10, prompt injection, data leakage, insecure output handling, excessive agency, guardrails, model risk, AI governance, and MITRE ATLAS.
- If the scheduled topic is Azure, create questions about Azure fundamentals, Entra ID, App Service, Defender, Sentinel, cloud models, identity, monitoring, and shared responsibility.
- If the scheduled topic is job search, create interview-prep, resume, LinkedIn, networking, behavioral interview, technical interview, and application strategy questions instead of technical certification questions.

Formatting rules:
- Do not use emojis anywhere, including headings, bullets, subject lines, checklists, or email titles.
- Use clean headings and readable formatting.
- Format must-know terms as: Term — definition.
- Do not merge terms and definitions together without separators.
- Avoid overly casual language.
- Make the writing clear, direct, practical, and professional.
- Make the newsletter dense with useful knowledge, but not an essay.
- Avoid generic motivation or filler.
- Prioritize exam recall, real-world understanding, job-readiness, interview readiness, hands-on learning, portfolio-building, and practical decision-making.
- Keep each newsletter around 1,200–1,500 words if needed for depth, but avoid unnecessary length.

Email rules:
- Send the completed newsletter directly by Gmail to: nruppatel439@gmail.com
- Do not create a draft unless direct sending is unavailable.
- If direct sending is unavailable, clearly state that direct sending is unavailable and create a properly formatted Gmail draft instead.
- Use the subject format: Daily Career Roadmap Newsletter - [Date] - [Topic]
- Do not use emojis in the subject line.      