<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=26&duration=3200&pause=900&color=22D3EE&center=true&vCenter=true&width=760&lines=Evidence+decides%2C+not+inference.;A+failed+precondition+reports+NOT+TESTED.;Scope+validation+is+enforced+in+code.;Confirm+a+weakness.+Never+weaponise+it." alt="Evidence decides, not inference" />

# NullCadre Research Library

**What informed the build of an AI-assisted platform for authorised penetration testing.**

[![Modules](https://img.shields.io/badge/offensive_modules-501-0ea5e9?style=for-the-badge&logo=target&logoColor=white)](TOOLS.md)
[![Gate](https://img.shields.io/badge/behind_the_gate-299-7c3aed?style=for-the-badge&logo=shieldsdotio&logoColor=white)](METHOD.md)
[![False positives](https://img.shields.io/badge/false_positive_rate-0_to_5%25-16a34a?style=for-the-badge&logo=checkmarx&logoColor=white)](METHOD.md)
[![Sources](https://img.shields.io/badge/sources-237_texts_·_637_domains-f59e0b?style=for-the-badge&logo=readthedocs&logoColor=white)](SOURCES.md)

[![Local AI](https://img.shields.io/badge/AI-local_model_only-be123c?style=flat-square)](#-local-ai-only)
[![Human in the loop](https://img.shields.io/badge/operation-human_in_the_loop-0f766e?style=flat-square&logo=keybase&logoColor=white)](#-human-in-the-loop-not-autonomous)
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

Built between **11 June and 4 October 2026**: 115 days, 1,654 commits, roughly 264,000 lines of code.

<div align="center">

| | | | |
|---|--:|---|--:|
| 🧩 **Offensive tool modules** | **501** | 🛡️ Modules behind the authorisation gate | 299 |
| 🧠 Reasoning-engine actions | 156 | ⚙️ Tool catalogue a run selects from | 70 |
| 📐 Core code | 166,417 lines | 🧪 Test code | 97,544 lines |
| 📁 Test files | 956 | 🎛️ Engagement profiles | 6 |

</div>

> [!IMPORTANT]
> **Measured false-positive rate: 0 to 5 per cent**, with one authenticated engagement producing 63
> findings and zero false positives. **219 detectors** are pinned in the test suite as provably
> silent on a benign input. Reaching that took longer than reaching coverage.

Test code is 59% of the volume of the code it protects. That ratio is deliberate: in this domain a
test that proves a detector behaves is part of the deliverable, not overhead.

<sub>Every figure above was counted from the source tree on 4 October 2026. Two earlier figures were
withdrawn in the process: a count of 178 battery phases, which no counting method in the tree reproduces,
and 37 engagement profiles, where the registry holds 6. The first is replaced by the tool catalogue a run
selects from, which is measurable; the second by the correct number.</sub>

## 📚 The library

<div align="center">

| | Document | Contents |
|:--:|---|---|
| 📖 | **[SOURCES.md](SOURCES.md)** | 237 books, papers and guides · 637 external domains · 16 specifications read in the original |
| 🧭 | **[METHOD.md](METHOD.md)** | How the work was done: the rules, and the failure each one prevents |
| 🧰 | **[TOOLS.md](TOOLS.md)** | The 501 modules, and the open-source tools they drive |
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

**💾 The platform's own code.** Its 501 modules are counted, never named or described: no source,
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
