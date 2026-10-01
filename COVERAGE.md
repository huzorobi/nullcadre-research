# Coverage

What the platform tests for. Classes are named because naming them is what establishes coverage, and
because a reader cannot judge an assessment without knowing its scope. How any of them is tested is not
described here.

Every class below is backed by deterministic checks whose verdicts are decided in code. The local model
reasons about the evidence those checks produce and deepens the search; it never decides that a weakness
exists.

---

## Reconnaissance and attack surface

Subdomain and DNS enumeration with hygiene validation. Single-page-application bundle analysis to recover
the real API surface a link crawler cannot see. GraphQL schema reconstruction where introspection is
disabled. Discovery-document and HTTP method-surface mapping. Mining of operator-supplied traffic captures
for the authenticated surface. OpenAPI and Swagger ingestion with coverage measurement. Parameter
harvesting. Origin discovery behind a CDN or WAF, with certificate and favicon correlation. Graded
technology fingerprinting. Organisation-to-asset scope expansion. Authenticated permission-map
reconnaissance.

## Access control

The class that pays most, and the one the platform was built around.

Two-account object-level authorisation testing (BOLA and IDOR). Function-level authorisation on both the
read and the write side. Message-level authorisation over non-REST transports. Mass assignment and
auto-binding. Cross-tenant isolation in multi-tenant applications. Excessive data exposure, where a caller
reaches its own object but receives more than it should. Object identifier analysis, including structured
and opaque identifier formats. Object-state authorisation, where a check holds on an active record but not
on an archived or draft one.

## Injection

SQL injection across eleven distinct families, among them error-based, header and cookie, path-segment,
ORDER BY and GROUP BY, object-relational and NoSQL operator abuse, JSON body traversal, blind and
conditional-error, filter evasion, search-engine query languages, XML and SOAP bodies, and data extraction
by set operation.

Beyond SQL: command injection, server-side template injection, expression-language injection, XML external
entities, LDAP and XPath injection, server-side includes, CRLF and header injection, host-header injection,
mail-header injection, path traversal and local file inclusion.

## Authentication, tokens and account takeover

JSON web token verification flaws, including algorithm confusion. SAML assertion tampering and signature
wrapping. OAuth redirect handling and flow integrity. Single-sign-on session handling. Multi-factor and
one-time-code integrity, covering account binding, single use and expiry. Password-reset flow abuse. Token
predictability, lifetime and blast radius. Privilege replay across sessions.

## AI and LLM application security

Mapped to the OWASP Top 10 for LLM applications.

Direct prompt injection. Indirect and stored prompt injection. Retrieval and vector-store poisoning.
Multi-modal injection. Agent memory poisoning across sessions. Multi-turn escalation. Zero-click injection
through automated email handling. Invisible-instruction carriers. Data exfiltration through rendered
content. Authorisation boundaries where a model mediates access. Code-interpreter sandbox escape. Tool and
function-call argument abuse.

## Client-side and web layer

Cross-user stored cross-site scripting, confirmed out-of-band. Sanitiser misconfiguration. Client-side
prototype pollution and template injection. Content-Security-Policy analysis. Web cache poisoning and web
cache deception. HTTP request smuggling and desync, detection only. Cross-origin resource sharing
misconfiguration. Open redirection. Clickjacking where an action of consequence is reachable. Cross-document
messaging flaws. Client-side path traversal.

## Server-side, cloud and network

Server-side request forgery, including reachability of cloud metadata services and the credential chain
that follows. Deserialisation of untrusted data. Subdomain, trust-allowlist and DNS-delegation takeover.
Race conditions and time-of-check-to-time-of-use flaws. Cloud storage and backend-service misconfiguration.
Container and orchestration posture. Exposed service and management-interface discovery. Secret exposure in
source, artefacts and client-side code. Business-logic and workflow abuse.

## The hunter

The deterministic battery is the floor. The hunter is a second pass that takes its findings as leads and
looks for what a fixed battery cannot reach: the chain that forms when two ordinary findings are combined,
the surface a template did not anticipate, the follow-up a human tester would try next.

It runs on a local model, inside the operator's estate. No client data is sent to a hosted service at any
point, including when the report is written.

Three limits hold it. It chooses only from a fixed catalogue of read-only actions, enforced in code, so an
action outside that catalogue cannot be taken whatever the model proposes. It stops at proof and never
escalates. And it does not decide anything: a lead it raises becomes a finding only when a deterministic
check confirms it.

## From finding to report

Impact scoring aligned to what was disclosed. Attack-chain synthesis, linking findings that compose into a
larger outcome. Professional reporting with reproduction steps, evidence paths, technical and business
impact, remediation and retest guidance. Coverage is stated in every report, including what was not tested
and why.

---

## What this page does not tell you

The classes are listed. The checks are not described: no payloads, no detection logic, no oracles, no
thresholds, no sequencing, and no account of which checks run against which surface or in what order. A
reader can see what an assessment covers. Nobody can reconstruct a check from this page.
