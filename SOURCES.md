# Sources

247 books, papers and guides; 637 distinct external sources, counted by domain, cited across the research; 17
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
| LLM-assisted triage | 4 | Filtering static-analysis findings with a model, and where that filtering fails |
| Authorisation taxonomy and reach | 2 | How authorisation flaws are classified and priced, and what makes one reachable at scale |
| Platform ecosystem research | 3 | A single application ecosystem's plugin corpus, its advisory record and its disclosure rules |
| Supply-chain advisory corpus | 1 | Malicious-package advisories across software ecosystems, read for where screening effort belongs |

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

## Standards and testing methods

These set the vocabulary findings are reported in.

| Source | Role |
|---|---|
| OWASP API Security Top 10 | API weakness classification, including authorisation |
| OWASP Web Security Testing Guide v4.2 | Coverage checklist for a web assessment |
| OWASP Testing Guide v4 | Earlier baseline |
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

This body of work was read closely and the answer shaped the design, which went the other way:
NullCadre is human-in-the-loop and its model runs locally. The literature below reports agents that
plan and act on their own; the reason for not building one is in the measurement cited above, where
a frontier model scored zero on the authorisation class that matters most commercially. An agent
that cannot be trusted with the verdict should not be given the engagement.

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

637 distinct external domains are cited across the research. The largest single source is the body of
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

## Added since October 2026: filtering a model's findings

Work after the first publication of this library concentrated on a single question: whether a language
model can be trusted to reduce a static analyser's false positives without introducing its own. The
answer in the literature is a qualified yes, and the qualifications are what shaped the build.

| Source | What it establishes |
|---|---|
| IRIS (ICLR 2025, arXiv 2405.17238) | Encoding the detected code path and its surrounding context lets a model classify true against false positives. Its false-discovery rate sat below the static analyser's alone, so the model did not add alarms of its own |
| ZeroFalse (arXiv 2510.02534) | Analyser output as structured input, with flow traces and per-weakness context. One prompt across all weakness classes performs worse than a prompt tailored to each |
| Path feasibility in LLM filtering (arXiv 2506.10322) | Model filters degrade on large dependency-heavy code unless asked explicitly whether the sink is reachable from attacker-controlled input |
| Reasoning versus non-reasoning models on analyser output (Semgrep study, eScholarship) | Reasoning models cut false positives further than models answering directly |

The conclusion carried into the platform is narrow and worth stating: **the model triages, it never
confirms.** It proposes which candidates deserve a human's attention. A deterministic check and a person
decide whether a weakness exists, which is the same division the rest of this library describes.

Disclosure economics were researched from primary sources over the same period: a CVE numbering
authority's public programme rules and vulnerability records, read to establish which weakness classes
are worth reporting and what a report must contain. Two findings shaped policy rather than code. Reports
generated without observation are treated as fabrication and carry escalating bans, which is why nothing
reaches a submission without evidence behind it. And the weakness class the first detector found is a
named false-positive source for that programme, which is why coverage is not the same as value.

## Added since October 2026: authorisation, priced rather than counted

The platform was built around access control, so the later research went at the part that had been
treated as settled: not how to find an authorisation flaw, but how to rank one and how to know when a
test proved nothing.

| Source | What it establishes |
|---|---|
| Bugcrowd Vulnerability Rating Taxonomy | The same flaw is priced an order of magnitude apart depending on whether the identifier is iterable or an opaque GUID. Severity follows reachability, not technique |
| The CWE catalogue, for the classes this work turns on | Missing authorisation, authorisation bypass through a user-controlled key, code injection and dynamic file inclusion. Used so a finding is classified by what it is, not by which detector found it |

Two conclusions went into code rather than prose. **Identifier reach became a scoring input**, because
an authorisation flaw on a sequential identifier can be exercised at scale and one on a random identifier
usually cannot, and the taxonomy prices that difference heavily. Where reach cannot be determined it is
recorded as unknown and stated, rather than assumed in either direction.

The second is a negative result and the more useful one. A measured study of language models on
weakness classes found a model scoring **zero across every trial on authorisation bypass**, while scoring
full marks on injection classes in the same harness. Authorisation is precisely where the model is no
help, which is why the authorisation work is deterministic and the model is only pointed at it.

A further review of the platform's own authorisation coverage, conducted against the source tree rather
than against its documentation, produced a seventeen-item gap list. Most items were already present. The
value of the exercise was the four that were not, and the discovery that two more existed but could never
report their own absence, which is the failure this library returns to repeatedly.

## Added since October 2026: one ecosystem, read at the source

A single application ecosystem was taken as a corpus to test whether weaknesses can be found by reading
source rather than probing a target: its public plugin repository, its advisory record, and the
disclosure rules of the authority that issues identifiers for it.

The reading established which weakness classes are worth the effort, and the answer was not the obvious
one. Missing authorisation is the most frequently rewarded class, but the subset reachable only by an
already-authenticated low-privilege user is a named false-positive source and is priced accordingly. The
value sits in unauthenticated file upload, file read, file deletion, option updates, code injection and
authentication bypass that reaches an administrative role.

Eight source-reading checks were built from that, each for one class and each answering a question about
code rather than about a response: an upload with no extension allowlist, an unprepared database query
built from request input, deserialisation of request input, deletion on a request-derived path, an
outbound fetch to a request-controlled address, a role or capability taken from the request, dynamic
inclusion on a request path, and a request that chooses its own identity. Candidates are confirmed
against an instance the operator owns, never against somebody else's installation.

The disclosure rules shaped policy more than code. Reports produced without observation are treated as
fabrication and carry escalating bans, so nothing reaches a submission without evidence behind it.

## Added since October 2026: reading a corpus without being misled by it

A public advisory corpus for software supply-chain compromise was read to decide where screening
effort belongs. It produced one usable result and one lesson about corpora that mattered more.

The usable result is that volume is not distributed as the industry discusses it. Across the corpus,
two ecosystems account for the overwhelming majority of malicious-package advisories; two others that
are frequently named alongside them carry a double-digit number of records between them. The obvious
confound was checked first, because "this ecosystem has no malware" and "nobody files advisories for
this ecosystem here" are indistinguishable from a count alone. The corpus carries both of the quiet
ecosystems as first-class, so the near-absence is a real difference in volume rather than a gap in
coverage. The conclusion was to add depth where the records are, not breadth across ecosystems.

The lesson is the reason this section exists. One month in the corpus held roughly fifty times the
advisories of its neighbours, which reads as a mass campaign and would be reported as one. It is an
artefact of how the data arrives: that month's records land on a handful of batch days with ordinary
volumes on every other day, and virtually all of them carry a single upstream credit line, while the
rest of the year carries it on about four fifths. The descriptions are not duplicates, so it is not
one campaign replicated either. **A publication date is not an incident date.** Any analysis that
treats the two as the same overstates that month by a factor of about fifty, and the correction is to
deduplicate by upstream source and use the campaign's own dates.

This is the same failure the method pages describe in a different setting: a count that is accurate
about its input and wrong about the world. It is recorded here because the figure was striking
enough to publish, and checking it took one query.

## Added since October 2026: beliefs that were wrong, and what corrected them

Five positions the platform had been working from were tested against primary sources and did not
survive. They are listed because the cost of each was real work aimed in the wrong direction.

- **A protection believed to close a whole injection class closes it only in one context.** The
  reasoning held for values used as quoted strings and not for values used as numbers or as lists of
  numbers. The ecosystem's own published advisory for exactly that pattern is what settled it, and it
  reopened a set of candidates previously written off.
- **A disclosure programme's payment model had been read as a contest for a few places.** Its own
  published rules, revised during the month, describe a guaranteed pool divided by contribution
  share, and they now reduce payment in proportion to a researcher's rejection rate. Volume
  submission is penalised directly, which inverts the strategy that had been assumed.
- **A held finding was out of scope at the programme it was being prepared for**, which its own
  published exclusions stated plainly and nobody had checked.
- **The effort had been aimed at the cheapest tier of a market.** Published figures put the core of
  the ecosystem at roughly twenty times the rate paid for the extensions that had been the focus.
- **Public proof-of-concept repositories carry fabricated identifiers.** Entries were found that
  describe weaknesses under identifiers no authoritative record contains. Anything ingested from such
  a source is now cross-checked against the authoritative record before it is believed.

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
| OWASP APTS (Autonomous Penetration Testing Standard) | What an autonomous tester must evidence, and the limits it must respect. Read in the original because the platform self-assesses against it rather than claiming conformance |

Vendor documentation for web servers, application frameworks, edge proxies and browsers was read on the
same principle: where a test's correctness depends on exactly how a component behaves, that behaviour
is read from the specification, never assumed. A test built on an assumption produces a confident
wrong answer, which is worse than no test.
