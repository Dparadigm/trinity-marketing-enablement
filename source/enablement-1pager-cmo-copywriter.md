> **CORRECTION (Ava 2026-09-23):** Scorecard targets = Trinity **CMO** + **Copywriter**. Ruby ≠ Copywriter.

# How to use CMO + Copywriter (1-pager)
**Audience:** Rachel Glaittli (Growth & Marketing Strategy Lead) · John Keever (paid/ops execution until confirmed)  
**Owner:** Mira (marketing ops) · **Status:** Draft for Dan → then John/Rachel  
**Date:** 2026-09-23 · **Companion:** `trinity-marketing-operating-model-draft.md`

---

## In one sentence
**CMO decides what matters this week. Copywriter drafts the assets. Humans Accept, stamp UTM, ship, and prove the outcome.**

---

## What each is for / not for

| Agent | For | Not for |
|-------|-----|---------|
| **CMO** (`cmo` · paradigmlife.abilityai.dev) | Diagnose spend/CPA/MQL gaps; force-rank the week; Daily Pulse + Monday pack / Synthesis Brief; hand briefs to Copywriter | Final copy, live posts, brand/compliance final say, auto-changing ad accounts |
| **Copywriter** (`copywriter` · branch `master`) | Turn an **approved** CMO brief into drafts in `./output/` for human gate | Choosing strategy, picking THE ONE THING, publishing without human approval |

**Legacy Drive naming:** “How Ruby Interprets the CMO Brief” + Ruby Approval Queue — **do not equate with Trinity Copywriter** until Dan clarifies (Ruby agent = social/video; Copywriter = writing authority).
**John’s review surface:** human gate on Copywriter `./output/` drafts (confirm live path with Dan/Ava).

---

## When (Mon / midweek / Fri)

### Monday (30–45 min) — Synthesis Brief ritual
**When:** Synthesis Brief lands ~**09:00 MT** (after the Monday pack). Open it first; ignore the rest of the firehose unless the brief points there.
**Mid-week:** Daily Pulse (~05:11 MT weekdays) for a 5-minute health check.

| Who | Does |
|-----|------|
| Rachel | Owns THE ONE THING + top 3–5 ranked items; assigns owners/times; rock alignment |
| John | Owns paid/ops execution items; confirms cap/pause moves |
| Both | Mark each ranked item **Accept / Defer / Kill** + one-line why |

### Mid-week (~15 min check) — Agent-assisted execution
- **Use CMO** when reallocating spend, diagnosing CPA/MQL/SQL gaps, competitor moves, SEO/trends, or needing a **new** brief for copy.
- **Use Copywriter** when a brief is Accepted, an asset is needed this week, and a human will review `./output/` before publish. **Do not** route marketing writing work to Ruby unless Dan expands scope (Ruby = social/video).
- **Use neither** for pure project management, legal/compliance final say, or one-off Slack coordination.

### Friday (~15 min) — Close the loop
For each Accepted item: shipped? Y/N · outcome metric moved? · next test · carry-over or Kill.

---

## What surfaces they open

| When | Open first | Open only if needed |
|------|------------|---------------------|
| Monday | **Synthesis Brief** (THE ONE THING + ranked: Owner / Why / Projected Outcome) | Synthesis Brief Diagnostic (number looks wrong) |
| Mid-week | Ads Audit / Marketing Summary / Strategic Analysis as the brief points; Copywriter draft + human gate | Competitor / Trends / SEO |
| Friday | Same week’s Accept log + Pulse weekly MQL stub (when available) | Full Monday pack re-read |

Ignore the rest of the CMO email firehose unless the brief points you there.

**Brief surfaces:** THE ONE THING · force-ranked list (Title / Source / Why / Projected outcome / Owner / Time / Tag) · Tags NEW · CARRY-OVER · CASCADE · JUDGMENT-CALL · contradictions · capacity.

---

## Accept / Defer / Kill rule

| Decision | Meaning | Required |
|----------|---------|----------|
| **Accept** | Execute in this window | Owner + due day + **testable outcome** (L1–L6) + UTM slug if traffic-creating |
| **Defer** | Valid, not this week | Why + earliest reopen week |
| **Kill** | Wrong, stale, or un-actionable | One-line why (feeds monthly “improve the machine”) |

**Hard rules**
1. No Accept without a projected outcome. Activity ≠ done.  
2. THE ONE THING completable by **Wednesday**; if not, Friday notes why.  
3. Carry-overs older than 2 weeks → Kill or re-scope (no infinite roll).  
4. If two reports disagree = JUDGMENT-CALL — don’t scale spend until resolved.  
5. If it isn’t in the brief and isn’t an emergency, it waits until next Monday.

---

## UTM stamp rule (brief-driven pushes)

Any Accept that can create or re-enter an MQL **must** stamp:

`utm_campaign=trinity_brief_<slug>`

- `<slug>` = kebab-case from the brief item title (ASCII, ~40 chars max).  
- Same campaign value on every creative for that item.  
- Full convention: `utm-convention-trinity-brief.md`.  
- Without the stamp, Pulse **cannot** attribute MQLs / speed-to-lead to the brief → scorecard cannot prove impact.

---

## Role cheat-sheet

| Lane | Owner |
|------|--------|
| Rocks / Accept-Kill / strategy | Rachel |
| Paid + ops execution of Accepted items | John |
| Enablement + scorecard ops | Mira |
| Weekly HubSpot outcome stub | Pulse |
| Rituals / L10 calendar slot | Atlas |

**Q4 note:** Rachel’s rock (ICP → CMO topic cards → Zoom polls → publish → measure with John) is the north star; weekly CMO/Copywriter usage should **serve that rock**, not compete with it. Ruby/Cornelius out of scope unless Dan expands.
