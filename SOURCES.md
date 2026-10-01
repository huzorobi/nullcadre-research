# Sources

237 books, papers and guides; 442 distinct external sources cited across the research; 16
specifications read in the original. Assembled between July and October 2026.

---

## Composition

| Collection | Items | Coverage |
|---|---|---|
| AI and cybersecurity | 97 | Autonomous penetration testing, LLM agents, the offensive-AI threat landscape |
| Practitioner guides | 47 | Individual web and API weakness classes, one per class |
| Academic survey bundle | 35 | AI in penetration testing, framed as ally or adversary |
| Bug-bounty practice | 22 | Hunting guides, reconnaissance handbooks, authorisation flaws |
| API authorisation | 16 | API security and broken object-level authorisation, including empirical studies |
| LLM security | 9 | Prompt injection, detection, defending model-integrated applications |
| Assessment practice | 4 | Reporting, cloud testing, exploitation frameworks |
| Automation | 3 | Bug-bounty automation and tooling method |
| Certification | 2 | Ethical-hacking syllabus and a supporting paper |
| Hardening | 2 | Container benchmark, authorisation practice for LLM-backed systems |

## Books and canonical texts

Read for method, not for payloads.

| Title | Subject |
|---|---|
| The Web Application Hacker's Handbook: Finding and Exploiting Security Flaws | Web application testing method (two editions) |
| Hacking APIs: Web API Pentesting Essentials | API enumeration, authorisation and abuse |
| Hacking: The Art of Exploitation, 2nd ed. (Erickson, 2008) | Exploitation fundamentals |
| The Tangled Web: A Guide to Securing Modern Web Applications | Browser security model and trust boundaries |
| Bug Bounty Bootcamp (Vickie Li) | Bounty method and reporting |
| The Hacker Playbook: Practical Guide to Penetration Testing | Engagement structure |
| Penetration Testing: A Hands-On Introduction to Hacking | Foundational assessment practice |
| Metasploit: The Penetration Tester's Guide | Exploitation framework method |
| Metasploit Basics for Hackers (OccupyTheWeb, 2021) | Framework practice |
| Black Hat Python | Offensive tooling in Python |
| Kali Linux Revealed (2021) | Platform and toolchain |
| Web Hacking 101 | Reported-vulnerability case studies |
| Cyber Autonomy: Automating the Hacker | Self-adaptive automated defence |
| Web Application Hacking: Advanced SQL Injection and Data Store Attacks | Injection depth |
| Ethical Hacking: Auditing Modern API Security | API assessment practice |
| Bug Bounty Playbook V2 · The Bounty Hunter Code · zseano's methodology | Practitioner method |
| Bug Bounty Automation with Python | Automating discovery |
| The Red Team Guide | Adversarial engagement structure |
| Certified Ethical Hacker (CEH) Foundation | Certification scope |

## Standards and testing methodologies

These set the vocabulary findings are reported in.

| Source | Role |
|---|---|
| OWASP API Security Top 10 | API weakness classification, including authorisation |
| OWASP Web Security Testing Guide v4.2 | Coverage checklist for a web assessment |
| OWASP Testing Guide v4 | Earlier methodology baseline |
| CWE | Weakness identifiers carried on every finding |
| CVSS | Severity scoring, aligned to disclosed impact |
| PTES | Engagement phase structure |
| MITRE ATT&CK | Technique vocabulary |
| NCSC: Common Cyber Attacks | Baseline threat framing |
| CIS Docker Community Edition Benchmark v1.1.0 | Container hardening |
| Guidelines for Secure AI System Development | Secure-by-design expectations |
| Securing LLM-Backed Systems: Essential Authorization Practices | Authorisation with a model in the loop |
| Zero Trust Agentic AI Security | Trust model for autonomous agents |

## Research literature

Roughly 120 papers and preprints. One result shaped the architecture more than any other: Fang et al.
(**arXiv:2402.06664**) measured a leading frontier model at **0% on authorisation bypass across five
trials, against 100% on SQL injection and CSRF**. Authorisation is therefore the class where a model alone is useless, which
is why the deterministic engine decides whether a weakness exists and the model only reasons about the
evidence it produced.

**Can language-model agents conduct penetration tests autonomously?**

- PentestGPT: an LLM-empowered automatic penetration testing tool
- PentestAgent: incorporating LLM agents into automated penetration testing
- RapidPen: fully automated IP-to-shell penetration testing with LLM-based agents
- PhantomRed: an autonomous AI-powered penetration testing framework
- COAPT: bridging the semantic-operational divide in autonomous testing
- HARMer: cyber-attack automation and evaluation
- Teams of LLM agents can exploit zero-day vulnerabilities
- From controlled to the wild: evaluation of pentesting agents
- AWE: adaptive agents for dynamic web environments
- Evaluating large language models' ability to automate security testing
- The rise and rise of LLM-powered pentesting
- AI-driven penetration testing for ARM systems: evaluation across four paradigms
- MITRE ATT&CK-driven threat hunting automated by a local LLM

**Can authorisation flaws be found automatically?**

- Detecting broken object-level authorization vulnerabilities
- Broken object-level authorization in the wild: an empirical study
- Automated broken object-level authorization attack generation
- Detection and prevention of insecure direct object references (two studies)
- An efficient approach for mitigating insecure direct object references
- Exposing IDOR vulnerabilities in academic publication platforms: a case study
- LLM-driven self-improving framework for security test automation

**How do systems with a model in the loop fail?**

- Automated prompt injection attacks
- Prompt injection attacks on agentic coding
- Prompt injection detection in LLM-integrated applications
- Prompt injection: risks and defence mechanisms
- Securing large language models from adversarial input
- HoneyLLM: a large-language-model-powered honeypot
- Enhancing security and applicability of local LLM-based systems
- ForensicLLM: a local large language model (Forensic Science International)

**What is the shape of the offensive-AI threat?**

Roughly 50 survey, policy and position papers, including a survey bundle on AI in penetration testing,
work on adversarial AI and cyber defence, autonomous cyberattack with security augmentation, and
systematic reviews of generative AI in offensive and defensive roles.

## Weakness classes studied

The practitioner corpus is 47 published guides, one per class. It was read to establish *coverage*:
which classes a credible assessment is expected to attempt, so that gaps can be named instead of left
silent.

- Server-side request forgery, including generator-specific and framework-specific variants
- XML external entities; server-side template injection
- SQL injection and NoSQL injection
- Cross-site scripting: reflected, DOM-based and blind
- Cross-site request forgery; insecure cookie policies
- Broken access control; broken authentication and two-factor bypass
- Business-logic errors; information disclosure
- JSON web token weaknesses; Content-Security-Policy bypasses
- Cross-origin resource sharing misconfiguration; open URL redirection
- Web cache poisoning; cross-document messaging
- Insecure file upload; remote code execution paths; Log4Shell
- GraphQL abuse; plugin and add-on ecosystems
- Cloud object-storage and backend-service misconfiguration
- Subdomain takeover; origin discovery behind a WAF; WAF bypass
- Reconnaissance: search-engine and repository dorking, internet-wide scanning services, wordlist
  construction, hidden parameter discovery, client-side JavaScript review, secret hunting

## Online sources

442 distinct external domains are cited across the research. The largest single source is the body of
publicly disclosed vulnerability reports.

| Source | Citations | Contribution |
|---|---|---|
| Public disclosed-report archives | 2,589 | Real reports: evidence standards, proof structure, class frequencies |
| Open-source repositories | 264 | Tool implementations, reference detectors |
| arXiv | 84 | Preprints on autonomous testing and model security |
| OWASP (main, cheat sheets, mobile) | 61 | Testing guides, API Top 10, defensive guidance |
| Web-security research labs | 53 | Original technique research |
| Security-vendor research | ~120 | Advisories and technique write-ups |
| Practitioner knowledge bases | ~40 | Community references |
| MITRE ATT&CK | 12 | Technique taxonomy |
| Cloud Security Alliance Labs | 12 | Agentic-AI and post-exploitation research |
| USENIX | 7 | Peer-reviewed security papers |
| Cloud-provider documentation | ~20 | Service behaviour relied on when reasoning about findings |
| Security press | ~50 | Disclosure timelines |

## Specifications read in the original

Primary specifications were read where a test's correctness depends on what a protocol actually
permits, not on what a scanner assumes.

| Specification | Why it was needed |
|---|---|
| RFC 9293 (TCP) · RFC 7540 (HTTP/2) | Transport behaviour underlying connection-level testing |
| RFC 7239 (Forwarded) | Which proxy headers an origin may legitimately trust |
| RFC 1918 · RFC 5737 | Private and documentation address ranges, used to keep fixtures off the public internet |
| RFC 7515 (JSON Web Signature) | What a signature does and does not guarantee |
| RFC 9700 (OAuth 2.0 best practice) | Authorisation-flow integrity |
| RFC 5321 · RFC 5322 · RFC 2047 | Mail transport and header encoding |
| RFC 7208 (SPF) | Sender authorisation |
| RFC 2109 (HTTP cookies) | Cookie scope and attribute semantics |
| RFC 4515 (LDAP filters) | Filter syntax |
| RFC 8615 (well-known URIs) | Discovery endpoints |
| RFC 3161 (timestamping) | Evidence timestamping |
| NIST SP 800-52 | TLS configuration guidance |

Vendor documentation for web servers, application frameworks, edge proxies and browsers was read on the
same principle: where a test's correctness depends on exactly how a component behaves, that behaviour
is read from the specification, never assumed. A test built on an assumption produces a confident
wrong answer, which is worse than no test.
