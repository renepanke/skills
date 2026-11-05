---
name: dr-house
description: Diagnose ambiguous, intermittent, or high-impact software bugs through differential diagnosis and controlled provocations. Use when symptoms have multiple plausible causes, reproduction is incomplete, or ordinary inspection has stalled; do not use for straightforward, already-localized fixes.
---

# Dr. House Debugging

Turn uncertainty into evidence. Diagnose the system; do not guess the fix.

## Establish the case

Collect observable facts before changing anything:

- Exact failure mode, error messages, stack traces, timestamps, and affected scope.
- Preconditions: inputs, user state, configuration, deployed and dependency versions, traffic level, and environment.
- What is reliably true, what is reported but unverified, and what is unknown.
- The smallest known reproduction, if one exists.

Write a one-sentence problem statement:

> Under [conditions], [component] produces [observable result], while [expected result] should occur.

Keep evidence separate from assumptions.

## Build and rank the differential

List distinct causal mechanisms that could explain all known symptoms. Prefer mechanisms over vague labels. Consider application state or logic, data shape or freshness, configuration and flags, cache/queue/retry/eventual consistency, dependency contracts and timeouts, resource limits, concurrency and ordering, and deployment/environment/network/identity differences.

For each live hypothesis, maintain a compact log:

| Hypothesis | Evidence it explains | Tension or contradiction | Discriminating observation | Confidence |
|---|---|---|---|---|
| H1 | … | … | If H1 is true, changing X produces Y. | low / medium / high |

Every live hypothesis must predict an observation that can distinguish it from at least one alternative.

## Hunt contradictions

Prioritize facts that do not fit the comfortable explanation. Ask why the issue affects only particular requests, users, nodes, regions, or versions; why it began when it did; what changed before the earliest known occurrence; and what remains normal despite the suspected subsystem supposedly failing.

Identify the single highest-value uncertainty to resolve next. A contradiction is usually more diagnostic than another confirming symptom.

## Run a controlled provocation

A **provocation** is a small, reversible, bounded change designed to make competing theories yield different observable outcomes. State it before running it:

> If **H** is true, then under controlled change **C**, observe **O**. If **O** does not occur, reduce confidence in **H**.

Useful provocations include bypassing a cache for one controlled request, replaying an exact input against a known version, changing concurrency in staging, stubbing one downstream dependency, adding correlation IDs and timing around a boundary, enabling a flag for a test subject, introducing bounded latency, or comparing a failing and working request field by field.

- Start locally or in staging whenever practical.
- Keep the experiment reversible and tightly scoped.
- Define the expected signal and safety boundary before running it.
- Record negative results as well as positive ones.
- Use production only when its risk is explicitly acceptable and containment is in place. Never create an uncontrolled production failure merely to get a signal.

If users are actively harmed, stabilize impact first; resume diagnosis after containment.

## Update the differential

After each experiment, record the observation, then raise, lower, split, or remove hypotheses accordingly. Select the next experiment for maximum discrimination rather than maximum activity. Do not treat an apparent fix as proof until its causal mechanism is explained.

A falsified hypothesis is progress when the test was capable of falsifying it. Continue until the leading explanation accounts for every material symptom without special pleading.

## Confirm, treat, and prevent relapse

Before implementing a fix, state the causal chain:

> Trigger → incorrect state or interaction → observed failure.

Confirm it with a minimal reproduction or targeted automated test that fails before the correction and passes afterward. Implement the smallest change that breaks this chain. Then add or strengthen regression coverage; verify relevant error handling, timeouts, cleanup, retries, and observability; check adjacent paths for the same assumption; and confirm the fix in the environment where the symptom occurred.

Conclude with the diagnosis, evidence, fix, verification, and any remaining uncertainty. Keep the hypothesis log so rejected explanations are not rediscovered.
