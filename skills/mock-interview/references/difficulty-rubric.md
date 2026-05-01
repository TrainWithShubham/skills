# Difficulty rubric — what a "good answer" looks like at each level

Use this to calibrate question difficulty *and* to grade the answer in the report. A junior who answers like a senior is hireable above level. A senior who answers like a junior is a no-hire even if their tenure says otherwise.

## Junior (0-2 years)

**What you're testing:** does the candidate know the vocabulary, can they follow a runbook, do they ask before doing something destructive?

**Strong-junior answer shape:**
- Defines the term correctly without rambling.
- Recognizes the scenario ("this looks like a stuck pod") and names the first 2-3 things to check.
- Says "I'd check the logs" — and can name *which* logs (`kubectl logs`, `kubectl describe`, not just "the logs").
- Knows when to escalate. "I'd check X, Y, Z, and if those don't reveal it I'd page the on-call senior."
- Honest about boundaries. "I haven't dealt with a multi-region failure, but I'd start by..." beats pretending.

**No-hire signals:**
- Confidently incorrect on basics (says ConfigMap when they mean Secret).
- Can't name a single command they'd actually run.
- Doesn't know what a P1 means.

## Mid (2-5 years)

**What you're testing:** can they own a service end-to-end, do they reason about tradeoffs, do they think operationally?

**Strong-mid answer shape:**
- Asks 1-2 clarifying questions before diving in. ("Is this prod or staging? Single region or multi?")
- Picks an approach and *names the alternative they're rejecting* and why.
- Thinks about the failure modes unprompted. "This works, but if the cache goes down we'd hammer the DB — I'd add a circuit breaker."
- Knows their stack's quirks. (e.g., "RDS read replicas have async replication lag, so for read-after-write we route to primary.")
- Can quantify roughly. "At 1000 RPS this is fine, at 10000 we'd hit connection pool limits around X."

**No-hire signals:**
- Reaches for "we'd add a load balancer" without knowing what it solves.
- Can't name one tradeoff for any decision.
- Has never read a postmortem they didn't write.

## Senior (5-8 years)

**What you're testing:** can they design a system that doesn't fall over, mentor a team, make decisions that cost money to reverse?

**Strong-senior answer shape:**
- Pushes back on the question if it's under-specified. "Before I design this — what's the read:write ratio? What's the RTO/RPO?"
- Designs in **layers** and explains each: data layer, control plane, observability, deployment, blast radius.
- Brings cost into the conversation unprompted. "This is the cheapest option that meets the SLO; here's the more expensive one and what extra it buys."
- Has opinions and explains them. "I'd avoid Kafka here — operational overhead doesn't justify the throughput we need; SQS + DLQ is enough."
- Names the metric they'd watch and the threshold for "this is broken".
- Tells a story when relevant — past incidents, decisions reversed, what they learned.

**No-hire signals:**
- Designs in pure happy path; doesn't volunteer failure modes.
- Cargo-cults. "We'd use Kubernetes" — for what?
- Can't articulate why their last team did X instead of Y.
- Talks about people they manage but not technical decisions they own.

## Staff+ (8+ years)

**What you're testing:** can they set technical direction across teams, identify problems nobody assigned them, simplify the org's hardest systems?

**Strong-staff answer shape:**
- Reframes the question. "The literal question is X, but the underlying problem is Y — let me address Y first."
- Thinks in **systems and second-order effects**. "If we ship this, the on-call burden for team B goes up — we should pair this with X."
- Picks battles. "We *could* do this, but we shouldn't — here's the cheaper bet."
- Names the simplest thing that works *and* the elegant thing, and recommends the simplest unless there's a real reason.
- Talks about influence and tradeoffs across teams, not just within one.
- Comfortable saying "I don't know" — but follows it with how they'd find out.

**No-hire signals:**
- All architecture, no operations.
- Designs systems they wouldn't be on-call for.
- Can't name a project they killed or de-scoped.
- Treats simplicity as a junior trait.

## Cross-level constants

Regardless of level, a strong answer:

- **Is structured.** Even a 30-second answer has a beginning, middle, end.
- **Names tradeoffs.** Anything important has at least one.
- **Mentions failure.** Real systems break; an answer that doesn't acknowledge this is incomplete.
- **Quantifies where possible.** "Slow" is junior; "p99 above 800ms" is senior.
- **Is honest.** "I haven't done that, but I'd reason about it like this..." is always better than bullshit.

## Calibration shortcut

If the answer would have come out of a textbook chapter, that's junior signal regardless of who said it.
If the answer references their actual experience and the *specific* context that made it the right call, that's senior signal regardless of who said it.
