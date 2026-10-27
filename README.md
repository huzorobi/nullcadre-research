<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=26&duration=3200&pause=900&color=22D3EE&center=true&vCenter=true&width=760&lines=Evidence+decides%2C+not+inference.;A+failed+precondition+reports+NOT+TESTED.;Scope+validation+is+enforced+in+code.;Confirm+a+weakness.+Never+weaponise+it." alt="Evidence decides, not inference" />

# NullCadre Research Library

**What informed the build of an AI-assisted platform for authorised penetration testing.**

[![Version](https://img.shields.io/badge/platform-v2.746.686-0f172a?style=for-the-badge)](#-the-work)
[![Modules](https://img.shields.io/badge/tool_modules-565-0ea5e9?style=for-the-badge&logo=target&logoColor=white)](TOOLS.md)
[![Gate](https://img.shields.io/badge/reach_a_live_target-311-7c3aed?style=for-the-badge)](METHOD.md)
[![Tests](https://img.shields.io/badge/tests_passing-12%2C536-22c55e?style=for-the-badge)](#)
[![False positives](https://img.shields.io/badge/false_positive_rate-0_to_5%25-16a34a?style=for-the-badge)](METHOD.md)
[![Sources](https://img.shields.io/badge/sources-246_texts_·_637_domains-f59e0b?style=for-the-badge&logo=readthedocs&logoColor=white)](SOURCES.md)

[![Local AI](https://img.shields.io/badge/AI-local_model_only-be123c?style=flat-square)](#-local-ai-only)
[![Human in the loop](https://img.shields.io/badge/operation-human_in_the_loop-0f766e?style=flat-square)](#-human-in-the-loop-not-autonomous)
[![No implementation](https://img.shields.io/badge/implementation-not_published-475569?style=flat-square&logo=git&logoColor=white)](#-scope-of-this-repository)
[![British English](https://img.shields.io/badge/written_in-British_English-1e3a8a?style=flat-square)](#)

</div>

---

This repository is the reading list and the method. It is published so that the research behind
NullCadre can be examined independently. It contains no implementation: nothing here is sufficient
to rebuild the platform.

> **The deterministic engine decides whether a weakness exists.** The hunter reasons about the
> evidence that engine produced and widens coverage. It never issues a verdict.

<table>
<tr><td width="50%" valign="top">

### 🧑‍💻 Human in the loop, not autonomous

The operator defines the scope, authorises it, launches every run and confirms any exploitation.
The software never decides on its own what to test, or whom to test it against.

</td><td width="50%" valign="top">

### 🔒 Local AI only

The hunter is the AI pass that takes the deterministic battery's findings as leads and deepens the
search. It runs on a model hosted inside the operator's estate, so no client data reaches a third
party: not the attack surface, not the findings, not the evidence, not the report text. There is no
hosted model anywhere in the loop.

</td></tr>
</table>

<div align="center">

**Platform** [nullcadre.com](https://nullcadre.com) · **Owner** [HuzoSecurity Ltd](https://huzosecurity.com), Robert Huzo

</div>

---

## 📊 The work

Built between **11 June and 27 October 2026**: 138 days, 2,127 commits, roughly 365,000 lines of code.

<div align="center">

| | | | |
|---|--:|---|--:|
| 🧩 **Offensive capabilities** | **444** | 🧰 Utilities, oracles and helpers | 116 |
| ↳ reach a live target | 311 | ↳ analyse collected material only | 133 |
| 🧠 Reasoning-engine actions | 157 | ⚙️ Third-party tools driven | 79 |
| 📦 Tool modules in total | 565 | 🔌 Reachable from a real entry point | 563 |
| 📐 Core code | 210,641 lines | 🧪 Test code | 154,401 lines |
| 📁 Test files | 1,177 | ✅ Tests passing | **12,536** |

</div>

**Each figure above states the question it answers, because no single number counts "capabilities"
honestly.** This page has published three wrong ones, and each is left on the record below rather
than quietly replaced.

It first said 565, the whole tool tree, which counts parsers and helpers as arsenal. It was
corrected to 312, the modules that pass scope validation - and that erases every detector which
reads collected material rather than touching a target: Active Directory, mobile packages, cloud
artefacts, and the source-analysis work that produced this project's published vulnerabilities.

**The third error was the interesting one, because it was invisible.** The census behind the
earlier split asked two questions of each module: does it construct a finding object, and does it
call the scope gate. Both are facts about how a module is *written*, not about what it *proves*. A
detector that reads collected source offline does neither - it contacts nothing, so it never
gates, and it hands a human a candidate to review rather than emitting a finding of its own. A
whole class of detectors was therefore filed as helper code, including the source-analysis arsenal
that earned this project's vulnerability credits. The census now also asks whether a module is
something an operator can actually run, which is the project's own working definition of a live
capability. That correction moved the count from 417 to **444**, and the offline half from 105 to
**133**.

A fourth figure moved by one, for a reason worth stating because it is the same mistake in
miniature: the gate census matched the gate's name anywhere in a file, so a module that *imports*
the gate and never calls it was counted as gated. **An import is not a call.** The gated figure is
311, not the 312 this page carried. The direction matters - that error inflates the authorised
surface, and it would hide a module that genuinely reaches a target with its gate missing, which
is the one thing this architecture must never get wrong.

So the figures are given as measurements rather than as a headline, and the two halves now sum to
the whole: **311 + 133 = 444**. The earlier split did not add up, and nobody noticed for weeks.
The remainder are utilities, oracles and shared helpers, and some of those are part of a
capability without being one on their own - which is precisely why the single number does not
exist. Anyone is free to disagree with where the line falls; they cannot be misled about where it
was drawn.

The same audit reports what the capability figure is worth: 563 of the 565 modules are reachable
from a real entry point, none fails to import, and none is without a test. Two are not reachable,
and they are counted here because a capability nobody can invoke is not one.

> [!IMPORTANT]
> **Measured false-positive rate: 0 to 5 per cent**, with one authenticated engagement producing 63
> findings and zero false positives. **222 detectors** are pinned in the test suite as provably
> silent on a benign input. Reaching that took longer than reaching coverage.

Test code is 73% of the volume of the code it protects. That ratio is deliberate: in this domain a
test that proves a detector behaves is part of the deliverable, not overhead.

### How it grew

Counted from the commit tree at each month end, not estimated.

```mermaid
%%{init: {"theme": "base", "themeVariables": {"xyChart": {"plotColorPalette": "#0ea5e9, #7c3aed"}}}}%%
xychart-beta
    title "Tool modules (bar) and test files (line), by month end"
    x-axis ["30 Jun", "31 Jul", "31 Aug", "30 Sep", "19 Oct", "27 Oct"]
    y-axis "Count" 0 --> 1200
    bar [47, 377, 409, 492, 553, 565]
    line [142, 515, 671, 905, 1109, 1177]
```

<div align="center">

| Month end | Tool modules | Test files | Commits | Tests per module |
|---|--:|--:|--:|--:|
| 30 June 2026 | 47 | 142 | 199 | 3.0 |
| 31 July 2026 | 377 | 515 | 826 | 1.4 |
| 31 August 2026 | 409 | 671 | 1,029 | 1.6 |
| 30 September 2026 | 492 | 905 | 1,580 | 1.8 |
| 19 October 2026 | 553 | 1,109 | 2,023 | 2.0 |
| **27 October 2026** | **565** | **1,177** | **2,127** | **2.1** |

</div>

The July step is the month the detector battery was built. What the later months add is not breadth but
proof: between September and October the module count rose by 15 per cent while the test files rose by
30 per cent, which is the shape intended. The last column is the one worth watching, because a platform
that adds detectors faster than it can show them behaving is accumulating a liability, not coverage.

The final week is the clearest example of that shape: 12 modules added against 67 test files. Almost
none of that week's work was new coverage. It was finding that existing coverage had been reporting
results it had not earned, and the tests are the record of each one being disproved.

### Where the reading went

<div align="center">

| Collection | | Items | Share |
|---|---|--:|--:|
| AI and cybersecurity | `████████████████████████████` | **97** | 39% |
| Practitioner guides | `██████████████` | **47** | 19% |
| Academic survey bundle | `██████████` | **35** | 14% |
| Bug-bounty practice | `██████` | **22** | 9% |
| API authorisation | `█████` | **16** | 6% |
| LLM security | `███` | **9** | 4% |
| Assessment practice | `█` | **4** | 2% |
| LLM-assisted triage | `█` | **4** | 2% |
| Automation | `█` | **3** | 1% |
| Platform ecosystem research | `█` | **3** | 1% |
| Certification | `█` | **2** | 1% |
| Hardening | `█` | **2** | 1% |
| Authorisation taxonomy and reach | `█` | **2** | 1% |
| Supply-chain advisory corpus | `█` | **1** | 0% |
| **Total** | | **247** | |

</div>

The weighting is deliberate. Two thirds of the reading sits in AI-and-security and practitioner method,
because the question this platform exists to answer is not which weaknesses exist but which of them a
machine can be trusted to judge. The smallest collections are the most recent: they are where the work
is now.

<sub>Every figure above was counted from the source tree at <b>v2.746.684</b> on 27 October 2026, by a
script that measures them rather than by hand, so the three repositories describing this platform cannot
drift apart again. Two figures are produced by executing the code rather than reading it, because the two
disagree: the action catalogue holds 157 entries and a regular expression over the same file counts 165.
Three figures published earlier were withdrawn for having no reproducible method: 178 battery phases, 37
engagement profiles where the registry holds 6, and a tool catalogue of 70, replaced here by the count of
third-party tools actually listed. The source counts are derived from the tables in SOURCES.md, so they can
be checked against the page itself.</sub>

## 📚 The library

<div align="center">

| | Document | Contents |
|:--:|---|---|
| 📖 | **[SOURCES.md](SOURCES.md)** | 247 books, papers and guides · 637 external domains · 17 specifications read in the original |
| 🧭 | **[METHOD.md](METHOD.md)** | How the work was done: the rules, and the failure each one prevents |
| 🧰 | **[TOOLS.md](TOOLS.md)** | The 444 offensive capabilities, and the open-source tools they drive |
| 🎯 | **[COVERAGE.md](COVERAGE.md)** | What the platform tests for, by weakness class |

</div>

## 🚧 Scope of this repository

This repository publishes the research and the method. The implementation stays with its owner.

That division is deliberate and complete: what is here is what a reader needs to judge the work,
and what is not here is what someone would need to copy it. The platform cannot be rebuilt from
this repository, and it is not intended to be.

<details>
<summary><b>What stays closed, and why</b></summary>

<br>

**🔧 Techniques and tactics.** The weakness classes studied are named, because that is what
establishes coverage. The way the platform tests them is not described, and neither are payload
logic, bypass families or verdict rules.

**💾 The platform's own code.** Its 565 tool modules are counted, never named or described: no source,
no logic, no thresholds, no sequencing, no decision rules.

**🔗 Orchestration.** The 79 third-party tools are listed because they are public software anyone
can install. Which drives which, in what order, under what conditions, and how their output becomes
a verdict is where the value sits, and is not described.

**🤐 Client work.** No programme names, hosts, target identifiers, findings or evidence appear.
Disclosing a finding without permission would breach the programmes under which the work was
authorised, and that obligation is treated as absolute.

</details>

## ⚖️ Licence

The documents in this repository are published for reference. The platform they describe is not
included and is not open source.

<div align="center">
<sub>Authorised testing only.</sub>
</div>
