<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=26&duration=3200&pause=900&color=22D3EE&center=true&vCenter=true&width=760&lines=Evidence+decides%2C+not+inference.;A+failed+precondition+reports+NOT+TESTED.;Scope+validation+is+enforced+in+code.;Confirm+a+weakness.+Never+weaponise+it." alt="Evidence decides, not inference" />

# NullCadre Research Library

**What informed the build of an AI-assisted platform for authorised penetration testing.**

[![Version](https://img.shields.io/badge/platform-v2.746.621-0f172a?style=for-the-badge)](#-the-work)
[![Modules](https://img.shields.io/badge/offensive_modules-553-0ea5e9?style=for-the-badge&logo=target&logoColor=white)](TOOLS.md)
[![Gate](https://img.shields.io/badge/behind_the_gate-312-7c3aed?style=for-the-badge)](METHOD.md)
[![Tests](https://img.shields.io/badge/tests_passing-11%2C198-22c55e?style=for-the-badge)](#)
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

Built between **11 June and 19 October 2026**: 130 days, 2,023 commits, roughly 336,000 lines of code.

<div align="center">

| | | | |
|---|--:|---|--:|
| 🧩 **Offensive tool modules** | **553** | 🛡️ Modules behind the authorisation gate | 312 |
| 🧠 Reasoning-engine actions | 157 | ⚙️ Third-party tools driven | 79 |
| 📐 Core code | 197,043 lines | 🧪 Test code | 139,482 lines |
| 📁 Test files | 1,109 | ✅ Tests passing | **11,198** |

</div>

> [!IMPORTANT]
> **Measured false-positive rate: 0 to 5 per cent**, with one authenticated engagement producing 63
> findings and zero false positives. **222 detectors** are pinned in the test suite as provably
> silent on a benign input. Reaching that took longer than reaching coverage.

Test code is 71% of the volume of the code it protects. That ratio is deliberate: in this domain a
test that proves a detector behaves is part of the deliverable, not overhead.

### How it grew

Counted from the commit tree at each month end, not estimated.

```mermaid
%%{init: {"theme": "base", "themeVariables": {"xyChart": {"plotColorPalette": "#0ea5e9, #7c3aed"}}}}%%
xychart-beta
    title "Offensive modules (bar) and test files (line), by month end"
    x-axis ["30 Jun", "31 Jul", "31 Aug", "30 Sep", "19 Oct"]
    y-axis "Count" 0 --> 1200
    bar [47, 377, 409, 492, 553]
    line [142, 515, 671, 905, 1109]
```

<div align="center">

| Month end | Offensive modules | Test files | Commits | Tests per module |
|---|--:|--:|--:|--:|
| 30 June 2026 | 47 | 142 | 199 | 3.0 |
| 31 July 2026 | 377 | 515 | 826 | 1.4 |
| 31 August 2026 | 409 | 671 | 1,029 | 1.6 |
| 30 September 2026 | 492 | 905 | 1,580 | 1.8 |
| **19 October 2026** | **553** | **1,109** | **2,023** | **2.0** |

</div>

The July step is the month the detector battery was built. What the later months add is not breadth but
proof: between September and October the module count rose by 12 per cent while the test files rose by
22 per cent, which is the shape intended. The last column is the one worth watching, because a platform
that adds detectors faster than it can show them behaving is accumulating a liability, not coverage.

### Where the reading went

<div align="center">

| Collection | | Items | Share |
|---|---|--:|--:|
| AI and cybersecurity | `████████████████████████████` | **97** | 39% |
| Practitioner guides | `██████████████` | **47** | 19% |
| Academic survey bundle | `██████████` | **35** | 14% |
| Bug-bounty practice | `██████` | **22** | 9% |
| API authorisation | `█████` | **16** | 7% |
| LLM security | `███` | **9** | 4% |
| Assessment practice | `█` | **4** | 2% |
| LLM-assisted triage | `█` | **4** | 2% |
| Automation | `█` | **3** | 1% |
| Platform ecosystem research | `█` | **3** | 1% |
| Certification | `█` | **2** | 1% |
| Hardening | `█` | **2** | 1% |
| Authorisation taxonomy and reach | `█` | **2** | 1% |
| **Total** | | **246** | |

</div>

The weighting is deliberate. Two thirds of the reading sits in AI-and-security and practitioner method,
because the question this platform exists to answer is not which weaknesses exist but which of them a
machine can be trusted to judge. The smallest collections are the most recent: they are where the work
is now.

<sub>Every figure above was counted from the source tree at <b>v2.746.621</b> on 19 October 2026, by a
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
| 📖 | **[SOURCES.md](SOURCES.md)** | 246 books, papers and guides · 637 external domains · 17 specifications read in the original |
| 🧭 | **[METHOD.md](METHOD.md)** | How the work was done: the rules, and the failure each one prevents |
| 🧰 | **[TOOLS.md](TOOLS.md)** | The 553 modules, and the open-source tools they drive |
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

**💾 The platform's own code.** Its 553 modules are counted, never named or described: no source,
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
