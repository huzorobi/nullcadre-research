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

## Proving a destructive class without performing it

Three weakness classes resisted black-box coverage for the same reason: confirming them means
destroying or altering a client's data. Deleting content to prove deletion works, writing a file to
prove an upload is accepted. A platform that stops at proof cannot do either, so those classes were
carried as declared gaps rather than quietly counted as clean.

They are now covered in the half that matters, and the method is the same each time: the
application is asked a question it answers honestly about its own permissions, and the answer is
read instead of the action being taken.

Object-level deletion authorisation is established from a read request alone. A recent platform
version publishes, for each object it returns, the permissions it would grant on that object,
computed by running its own permission check with that object bound. A delete permission in that
answer is the application stating it would delete that specific object for the caller who asked,
and nothing but a read was sent. A test asserts the request set actually used contains no write
verb, so the claim is enforced rather than described.

Upload authorisation is established with nothing written. The platform's documented ordering places
its permission check before any handling of the submitted data, and its data handling returns an
error before anything is stored. A request carrying no data therefore passes the permission check
and fails afterwards, which proves the caller held the upload permission while leaving no file and
no record behind.

What is still not covered is stated in both cases, because an authorisation proof is not a
confirmation: that the deletion would succeed, and that a dangerous file type would be accepted.
Neither is claimed, and the reports say so.

A fourth class, deliberately planted access in third-party extension source, is reviewed offline
from publicly downloadable code, so no client system is involved at all. It reports indicators with
the line of source attached and never a verdict, because an accusation of intent is not something
source can establish: a debugging leftover, an upstream oddity and a deliberate door can look
identical, and a human decides which.

## Coverage statements survive the whole pipeline

A gap that reaches no report is a gap the client is told does not exist. An audit of every stage
between a check and the finished report found that statements about what was NOT tested were being
discarded at six separate points, including one where an aggregator turned a precondition failure
into an affirmative "nothing here" and the reasoning engine then stopped pursuing the class. Each
point now carries the statement through, and the audit itself is a test, so a new check wired
without its coverage channel fails rather than shipping a silent gap.

Identifier reach also contributes to priority now. Whether the identifier in an authorisation flaw
is enumerable or opaque decides whether every object is reachable by counting or only one that an
attacker already knows, and that distinction moves the priority of an otherwise identical finding.
An identifier that cannot be read from the evidence changes nothing and says so.

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
