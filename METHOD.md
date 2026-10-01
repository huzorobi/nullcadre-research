# How the work was done

The method is the part worth examining, and it can be stated without describing any implementation.
Each rule below exists because its absence produced a specific, expensive failure during development.
Each is now enforced by a test rather than by intention.

---

## Evidence decides, not inference

- **A finding is only a finding if the request that proves it was executed.** A keyword match proves a
  string exists — not that the code runs, and not that anything reaches it.
- **The deterministic engine alone decides whether a weakness exists.** The language model reasons
  *about* evidence the engine produced and never produces a verdict. This follows from measurement, not
  taste: models score near zero on authorisation reasoning while scoring well on injection classes, so
  the one class where a model is useless is precisely the class that pays.
- **Severity follows what was disclosed** — the sensitivity of the data, whether the action was read or
  write, whether the identifier was reachable at scale — never the ingenuity of the method.
- **Vocabulary is kept precise.** An observation is not a hypothesis, a hypothesis is not a potential
  vulnerability, and a potential vulnerability is not a proven weakness. Collapsing those steps invites
  a reader to assume proof that does not exist.

## Absence of evidence is not evidence of absence

- **A check whose preconditions failed reports NOT TESTED.** It never reports a clean result. Telling a
  client their authorisation is sound on the strength of a test that never ran is the most damaging
  thing a platform of this kind can do.
- **A control must be capable of failing.** Every guard is tested against the exact defect it exists to
  catch, because a guard that cannot fail is worth nothing — and a guard that fires on a run which
  demonstrably worked is equally worthless, since it teaches the reader to ignore it.
- **A finding that disappeared because the target disappeared is not remediated.** If a run lost its
  target or skipped a check, the result is *not re-observed*, not *resolved*.
- **Nothing is described as fixed.** An external tester cannot see a patch. The strongest honest claim
  is that a weakness was not rediscovered using the original method and a stated set of variants.

## The false-positive problem, and the cost of solving it

This is where most of the engineering time went, and it is the result the platform is actually judged on.

**The measured false-positive rate is 0 to 5 per cent.** On one authenticated engagement the run produced
63 findings with zero false positives. That number is not a tuning setting; it is the output of a standing
invariant and a great many hours of chasing individual wrong answers to their root cause instead of
suppressing them.

The invariant: **no detector ships until it is proven silent on a benign input.** 71 detectors are
currently pinned that way in the test suite — each paired with a known-clean case and failing CI if it
ever speaks when it should not. The rule exists because a detector's false-positive behaviour is
otherwise discovered on a client's live target, which is the most expensive place to find it and the one
place it cannot be undone.

Two refinements were learned the hard way and now apply to every check:

- **A fixture that is silent because nothing ran proves nothing.** Several checks appeared to behave
  until it emerged that their preconditions had failed, so the quiet was absence of testing rather than
  absence of a flaw. Every clean fixture now asserts the detector genuinely executed before it asserts
  the detector stayed quiet.
- **A guard must be able to fire and able to stay quiet.** Each is tested against the exact defect it
  exists to catch *and* against a case that must not trigger it, because a guard that cries wolf teaches
  the reader to ignore it — the same damage as a false all-clear, pointing the other way.

Reaching single-digit false positives took far longer than reaching coverage. Coverage is additive: a new
check adds a class. Precision is not: every wrong answer has to be traced to the assumption that produced
it, and the fix verified against the engagements that exposed it. That work is invisible in a feature
list and is the reason the platform's output can be handed to a client.

## Written is not working

- **A module that is finished, tested and exported is still dead code** until a real entry point
  executes it and produces output. Verification means running it, not reading it.
- **Every capability claim carries the date it was counted.** A claim about current state silently
  expires, so the date is written where a reader will see it.
- **A reduction in coverage is treated as a regression.** Tests are not removed to make a change pass.

## Authorisation is enforced, not promised

- **Scope validation runs in code, fails closed, and precedes every action that touches a host.** It is
  not a prompt instruction, because an instruction can be reasoned around and a return value cannot.
- **Testing stops at proof.** The platform demonstrates a weakness and collects evidence; it does not
  escalate, persist, or move laterally. That ceiling is deliberate, and it is what makes the output
  usable by buyers in regulated sectors.
- **The reasoning model runs locally.** Information about a client's systems does not leave the
  operator's estate, including for report writing.
- **Every report states what was not tested, and why.** Coverage is stated honestly or the report is
  not finished.

---

## Why these rules exist

Each one was learned by getting it wrong first. The pattern that recurred most was not a missing
feature but a silent success: a check that returned nothing because it never ran, a module that was
complete but unreachable, a guard that could not fail, a figure that had been true months earlier. None
of those announce themselves — every local signal reads green — which is why each is now pinned by a
test that fails loudly instead of by a habit that can lapse.
