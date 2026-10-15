---
name: durable-writing
description: Write anchored text a stranger parses cold — comments, docstrings, tests, docs, tickets, runbooks, messages.
---

Write _anchored_ text: every proper noun defined in place or replaced by its
mechanism, so the sentence parses with the thread covered. The writer owns
this; never assume the reader was in the room.

## Four practices

1. **Name the mechanism, not the moment.** A date explains when, never why.
   Weak: "(decided Tuesday) retry three times."
   Anchored: "retry three times, then dead-letter — the downstream call fails
   silently on the fourth concurrent attempt (link to incident)."
2. **Define or replace.** People, ticket numbers, IDs: define in place or swap
   for what they stand for.
   Weak: "ask Priya, then merge #412."
   Anchored: "ask the owning team (address in `OWNERS`), then merge the retry PR."
   Synthetic identifiers always (privacy and clarity agree here).
3. **Say the work, not the workflow.** No methodology names, phase names, or
   session shorthand.
   Weak: "validated at layer 3." Anchored: "validated where the request is parsed."
   Weak: "a stage-2 item." Anchored: the work itself ("weekly error report").
4. **Sparse sentences, positive actions.** One idea per sentence — the
   "X, not Y" contrast packs two judgments into one line and reads dense.
   State what to do; cut the rejected half unless omitting it misleads.
   Weak: "Fix the lookup, not the data."
   Anchored: "Fix the receiving lookup; it returns ambiguous matches."
   Weak: "Do NOT post $49.68."
   Anchored: "Leave the $49.68 unposted. The posted $110.37 already equals the net."

## Done when

List every proper noun, date, ticket number, and methodology term in the text;
each is defined in place or cut. Then cover the thread and re-read: anything
still needing it dies. Done = zero unaccounted names, cold parse clean.

## Cold review (for text others will act on)

Self-review misses what familiarity hides. For reports, runbooks, handoffs —
anything where a stranger must act — hand the text to a reviewer with no
thread context (a subagent, or a second pass with the thread covered) and one
instruction: identify each observed failure, verify why it is a failure, and
confirm each stated next action is executable from this document alone
(locate the evidence, recompute the numbers, trace each identifier).
Verification only: the reviewer reads, never writes — no merges, posts,
messages, or state changes. Fix every gap it finds, or mark the exact pull
that closes it. One round suffices; repeat only if the fixes added new
claims. Routine comments skip this — the self-check above is their bar.
