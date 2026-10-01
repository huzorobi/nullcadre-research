# NullCadre — Research Library

**What informed the build of an AI-assisted platform for authorised penetration testing.**

This repository is the reading list and the method. It is published so that the research behind
NullCadre can be examined independently. It contains no implementation: nothing here is sufficient
to rebuild the platform.

Owner: HuzoSecurity Ltd. Counted from the source tree on 2026-10-01.

---

## The work

Built between **11 June and 1 October 2026** — 112 days, 1,587 commits, roughly 253,000 lines of code.

| | |
|---|---|
| Core code | 161,317 lines |
| Test code | 91,808 lines |
| Test files · passing tests | 909 · 7,931 |
| Offensive tool modules | 492 |
| Modules behind the authorisation gate | 294 |
| Deterministic battery phases | 178 |
| Reasoning-engine action catalogue | 156 specifications, all read-only |
| Third-party tools wrapped | 87, all open source |
| Engagement profiles | 37 |

Test code is 57% of the volume of the code it protects. That ratio is the point rather than a side
effect: in this domain a wrong answer delivered confidently is worse than no answer, so the harness
that proves a detector behaves is part of the deliverable, not overhead.

## The library

| Document | Contents |
|---|---|
| [SOURCES.md](SOURCES.md) | 237 books, papers and guides · 442 external sources · 16 specifications |
| [METHOD.md](METHOD.md) | How the work was done — the rules, and the failure each one prevents |
| [TOOLS.md](TOOLS.md) | The 87 open-source tools studied and integrated |

## What this repository deliberately omits

It shows the scale of the work, the sources behind it and the method. It does not describe how any of
it is implemented. What is published is what a reader needs in order to judge the work; what is
withheld is what someone would need in order to copy it.

- **No techniques or tactics.** No payloads, no detector logic, no bypass chains, no verdict rules.
  The weakness classes studied are named; how the platform tests them is not.
- **No custom scripts or detector internals.** The platform's own modules are counted, never named or
  described. No source, no logic, no thresholds, no sequencing, no decision rules.
- **No orchestration.** The third-party tools are listed because they are public software anyone can
  install. Which feeds which, in what order, and how their output becomes a verdict is not described —
  and that is where the value sits.
- **No engagement data.** No client or programme names, no hosts, no target identifiers, no findings
  and no evidence. Disclosing a finding without permission breaches the programmes under which the
  work was authorised, so none appears here.

## Licence

The documents in this repository are published for reference. The platform they describe is not
included and is not open source.
