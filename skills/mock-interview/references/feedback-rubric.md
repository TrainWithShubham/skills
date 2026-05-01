# Feedback rubric — how to grade and write the report

The candidate reads this report and acts on it. If the feedback is vague, they'll prep on the wrong things. Specific, candid, cited-to-their-words feedback is the entire value of the mock.

## The five axes

Grade every answer on these, even if you only call out 1-2 in the report:

1. **Correctness.** Did they answer the question that was actually asked? Or did they answer an adjacent one they were more comfortable with?
2. **Depth.** Did they reason from first principles, or recite? "We'd use Redis" is recitation; "we'd use Redis because the access pattern is read-heavy with low cardinality on keys, and we want sub-ms latency that the DB can't give us" is reasoning.
3. **Tradeoffs.** Did they consider an alternative they're explicitly rejecting? Or jump to the first answer that came to mind?
4. **Operational thinking.** Did they think about how it fails, gets debugged, gets observed, gets deployed, gets rolled back? Or did they design only the happy path?
5. **Communication.** Was the answer structured? Could you tell where they were going? Did they signal the shape of the answer ("I'll cover three things — X, Y, Z") before diving in?

A senior+ candidate hits 4-5 of these per answer. A mid hits 3. A junior hits 2. If the candidate is hitting their level on every axis, the verdict is Pass.

## Writing the per-question analysis

**"Your answer (summary)" — paraphrase, don't quote.**
Two sentences max. The candidate already knows what they said; the goal is to anchor the analysis. "You opened with caching, then pivoted to load balancing, then ran out of road on the database." beats a transcript dump.

**"What landed" — be specific.**
"You correctly identified that the bottleneck is the DB, not the app tier" is signal. "Good understanding of the system" is filler.

**"What didn't" — cite their actual phrasing where it helps.**
"You said 'we'd just scale horizontally' — the question is *what* scales, and the DB doesn't shard itself. That's the gap." This beats "could have gone deeper on scaling."

**"Strong-candidate answer" — write it the way the candidate would deliver it, not as a textbook.**
- 60-90 seconds spoken.
- Has structure ("three things: X, Y, Z").
- Names one tradeoff and one failure mode.
- References a real-world fact when appropriate ("DynamoDB has 400KB item limit, so we'd...").
- Doesn't include every possible angle — strong answers are *selectively* deep, not exhaustive.

**"What the interviewer would write down" — be the interviewer.**
Tier-specific signal. e.g., for MANG senior: "Reached for managed service before reasoning from primitives — would push back in debrief."

## Pattern detection across the session

Look for things that show up in 2+ questions. These are the highest-leverage prep targets.

**Pattern types to watch for:**
- **Knowledge gaps that span topics** — e.g., consistently weak on networking concepts even when the question is about K8s or about AWS.
- **Habits that hurt** — always reaches for managed service first; always handwaves on cost; never volunteers failure modes; never asks clarifying questions.
- **Habits that help** — always quantifies; always names tradeoffs; always thinks about observability — call these out too, the candidate should keep doing them.
- **Tier mismatch** — senior-tier candidate giving mid-tier answers (or vice versa). Worth flagging because their stated level may be miscalibrated.

Surface 2-4 patterns. More than that and the report becomes a wall of text and the candidate ignores all of it.

## Tier-by-tier verdict

This is the line that gets remembered. Don't soften it.

- **Pass:** This person clears the bar today. Could go to the real loop.
- **Borderline:** Could go either way; depends on the panel and the day. Specific weak spots are fixable in 2-4 weeks.
- **Fail:** Not ready today. 1-3 months of focused prep on specific gaps.

A candidate who's "Pass at Service / Borderline at Product / Fail at MANG" knows exactly where to aim. A candidate who's "Pass everywhere" with no caveats has nothing to prep — that report is useless.

If they're genuinely strong everywhere, say so — but cite *what* makes them strong (specific answers from this session) and what would still get them caught at MANG (one specific gap).

## 7-day prep plan

Tie every day to a gap from *this* interview. "Day 3: review StatefulSet upgrade strategies (you got tripped up on Q2 — see the strong answer above for what to study)" beats "Day 3: study Kubernetes."

When recommending resources, prefer ones with concrete next steps:
- Specific KubeCon talks with timestamps.
- Specific docs pages, not "read the AWS docs".
- Specific book chapters, not "read the SRE book" (but if you do recommend SRE books: *Site Reliability Engineering* ch. 6 monitoring, ch. 11 on-call, ch. 22 cascading failures).
- Specific labs (KillerCoda for K8s, AWS skill builder, Terraform Associate practice exams).

## Drills

Three drills, every one of them concrete enough to start tomorrow.

Bad: "practice system design"
Good: "Whiteboard a 100M DAU URL shortener in 25 minutes, no Googling. Time yourself. Record yourself if you can."

Bad: "study Kubernetes"
Good: "On a Killercoda playground, deliberately break a Deployment four ways (image pull error, OOM, readiness probe fail, network policy block) and time how fast you find each. Target: under 90 seconds each."

## What to avoid in the report

- "Great session!" — they paid for honesty, not encouragement.
- "You've got this!" — they don't know yet, and neither do you.
- Generic advice that could appear in any candidate's report. If you remove the candidate's name and the report still applies to anyone, it's not useful.
- Hedge phrases ("you could probably...", "it might help to..."). Just say it.
- Long lists. Three patterns, three drills, seven prep days. Anything more and they won't act on it.

## Tone

Direct, specific, kind in the way a senior teammate is kind — by telling you the truth before you walk into the room. Not warm. Not harsh. Useful.
