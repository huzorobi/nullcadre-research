# NullCadre Research Library

**What informed the build of an AI-assisted platform for authorised penetration testing.**

This repository is the reading list and the method. It is published so that the research behind
NullCadre can be examined independently. It contains no implementation: nothing here is sufficient
to rebuild the platform.

**NullCadre is human-in-the-loop, not autonomous.** The operator defines the scope, authorises it,
launches every run and confirms any exploitation. The software never decides on its own what to
test or whom to test it against.

**The hunter runs on a local model, on the operator's own hardware.** The hunter is the AI pass that
takes the deterministic battery's findings as leads and deepens the search. It runs on a model hosted
inside the operator's estate, so no client data reaches a third party: not the attack surface, not the
findings, not the evidence, and not the report text. There is no hosted model anywhere in the loop.

The deterministic engine decides whether a weakness exists. The hunter reasons about the evidence that
engine produced and widens coverage. It never issues a verdict.

Platform: **[nullcadre.com](https://nullcadre.com)**
Owner: **[HuzoSecurity Ltd](https://huzosecurity.com)**, Robert Huzo.

Figures counted from the source tree on 2026-10-01.

---

## The work

Built between **11 June and 1 October 2026**: 112 days, 1,587 commits, roughly 253,000 lines of code.

| | |
|---|---|
| Core code | 161,317 lines |
| Test code | 91,808 lines |
| Test files · passing tests | 909 · 7,931 |
| **Offensive tool modules** | **492** |
| Modules behind the authorisation gate | 294 |
| Deterministic battery phases | 178 |
| Reasoning-engine action catalogue | 156 specifications, all read-only |
| Engagement profiles | 37 |

**Measured false-positive rate: 0 to 5 per cent**, with one authenticated engagement producing 63
findings and zero false positives. 71 detectors are pinned in the test suite as provably silent on benign
input. Reaching that took longer than reaching coverage. See [METHOD.md](METHOD.md).

Test code is 57% of the volume of the code it protects. That ratio is deliberate: in this domain a wrong answer delivered confidently is worse than no answer, so the harness
that proves a detector behaves is part of the deliverable, not overhead.

## The library

| Document | Contents |
|---|---|
| [SOURCES.md](SOURCES.md) | 237 books, papers and guides · 442 external sources · 16 specifications |
| [METHOD.md](METHOD.md) | How the work was done: the rules, and the failure each one prevents |
| [TOOLS.md](TOOLS.md) | The 492 modules, and the open-source tools they drive |
| [COVERAGE.md](COVERAGE.md) | What the platform tests for, by weakness class |

## Scope of this repository

This repository publishes the research and the method. The implementation stays with its owner.

That division is deliberate and complete: what is here is what a reader needs to judge the
work, and what is not here is what someone would need to copy it. The platform cannot be
rebuilt from this repository, and it is not intended to be.

- **Techniques and tactics stay closed.** The weakness classes studied are named, because that is
  what establishes coverage. The way the platform tests them is not described, and neither are payloads,
  logic, bypass families or verdict rules.
- **The platform's own code stays closed.** Its 492 modules are counted, never named or described: no
  source, no logic, no thresholds, no sequencing, no decision rules.
- **Orchestration stays closed.** The 87 third-party tools are listed because they are public software
  anyone can install. Which drives which, in what order, under what conditions, and how their output
  becomes a verdict is where the value sits, and is not described.
- **Client work stays confidential.** No programme names, hosts, target identifiers, findings or
  evidence appear. Disclosing a finding without permission would breach the programmes under which the
  work was authorised; that obligation is treated as absolute.

## Licence

The documents in this repository are published for reference. The platform they describe is not
included and is not open source.
