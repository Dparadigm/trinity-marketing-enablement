# Trinity Marketing Operating Model — Draft (for Dan review)
**Owner:** Mira (marketing ops) · **Audience:** Dan → then John Keever & Rachel Glaittli  
**Status:** Draft — do not send to John/Rachel Glaittli Dan confirms  
**Date:** 2026-09-23  
**Collaborators:** Atlas (rituals/ownership), Ava (Ability backlog), Pulse (HubSpot outcomes)

---

## 1. What we’re optimizing for (outcome ladder)

North star: **company revenue** influenced by marketing. Intermediate outcomes the agents already speak in (from Synthesis Briefs + Pulse HubSpot):

| Tier | Outcome | Source of truth |
|------|---------|-----------------|
| L1 | Spend efficiency (CPA, weekly cap adherence, pause/realloc) | CMO Ads Audit + Monday Strategic Analysis |
| L2 | Traffic → conversion (WealthScore completes, LP CTR) | GA4 / portal / Hotjar + CMO reports |
| L3 | MQL volume + quality (High vs Standard intent) | HubSpot (Pulse) |
| L4 | Speed-to-lead + SLA + contact rate | HubSpot first CALL (Pulse) |
| L5 | MQL → SQL / appointment | HubSpot + Sales (gap: Pulse needs stage props) |
| L6 | Pipeline → closed / commission | CRM deals (gap) |

**Rule:** Activity without a tier outcome is optional. Brief items without a testable outcome do not count as “done.”

---

## 2. What the agents are (and aren’t)

### CMO / Trinity marketing intelligence
**Surfaces (typical weekly pack):**
- Monday Strategic Analysis (THE ONE THING)
- Weekly Marketing Summary
- Weekly Ads Audit
- Competitor / Trends / SEO (as available)
- **Synthesis Brief** — force-ranked work plan for Marketing Monday L10
- Optional: Synthesis Brief Diagnostic (lineage)
- Playbooks: content calendar, email/copy briefs handed to copywriter

**What it’s for:** Diagnose, prioritize, quantify, and assign the week’s marketing work with projected outcomes.  
**What it’s not for:** Writing final copy, posting live, replacing human judgment on brand/compliance, or auto-changing ad accounts.

### Copywriter agent (Ruby / copywriter handoff)
**Surfaces:** Platform-ready drafts from a CMO/email/copywriting brief (`/plan-from-brief` style handoff).  
**What it’s for:** Turn an approved brief into draft assets fast.  
**What it’s not for:** Choosing strategy, picking THE ONE THING, or publishing without human approval.

**Existing explainer:** “How Ruby Interprets the CMO Brief - Content Flow Explainer” (Drive).

---

## 3. Enablement — How / What / When / What it surfaces

### Monday (30–45 min) — Synthesis Brief ritual
| Who | Does |
|-----|------|
| Rachel | Owns THE ONE THING + top 3–5 ranked items; assigns owners/times |
| John | Owns paid/ops execution items in the brief; confirms cap/pause moves |
| Both | Mark each item: **Accept / Defer / Kill** with one-line why |

**Surfaces they must open:** Synthesis Brief (primary). Diagnostic only if a number looks wrong.

### Mid-week (15 min) — Agent-assisted execution
- **Use CMO** when: reallocating spend, diagnosing CPA/MQL/SQL gaps, competitor moves, SEO/trends, needing a new brief for copy.
- **Use Copywriter** when: brief exists, asset needed this week, human will review before publish.
- **Don’t use either** when: pure project management, legal/compliance final say, or one-off Slack coordination.

### Friday (15 min) — Close the loop
For each Accepted item: shipped? Y/N · outcome metric moved? · next test.

---

## 4. Attribution bridge (Pulse)

**Gap:** HubSpot cannot tag contacts to a Trinity brief ID today.  
**Fix (no HubSpot schema change):** stamp brief-driven campaigns with:

`utm_campaign=trinity_brief_<slug>`  
(+ consistent `utm_source` / `utm_medium` / `utm_content`)

Pulse can then report weekly MQL + speed/SLA on those campaigns. Pulse drafting UTM convention + weekly MQL stub.

---

## 5. Scorecard — John & Rachel (usage → impact)

### A. Usage & collaboration (leading)
- Synthesis Brief opened / Accepted items count (Rachel / John)
- % of THE ONE THING completed by Wednesday
- Copywriter briefs started → drafts reviewed → live (cycle time)
- Agent sessions logged (light honor system until telemetry exists)

### B. Brief impact (leading → lagging)
- Accepted items with defined test metric
- Items completed in-window
- Carry-over age (stale carry-overs = weak impact)

### C. Funnel outcomes (Pulse weekly stub)
- MQL count + High/Standard
- Source / UTM (incl. `trinity_brief_*`)
- First-CALL contact rate + p50 hours-to-CALL
- SLA hit vs slip
- SDR coverage (assigned vs blank)

### D. Purpose / intention (qualitative, monthly)
One sentence per person: *“This week the brief existed to ___ so that ___.”*  
Tied to L1–L6 tier above.

### E. Improve the machine (monthly)
- Which brief recommendations were wrong / un-actionable?
- Feedback into Ability (via Ava) — do not clone CMO/copywriter agents
- UTM hygiene score (% brief-driven pushes correctly tagged)

**Scoring principle:** Weight **C + B** over **A**. Usage without outcome movement is a coaching signal, not a win.

---

## 6. Role split (proposed)

| Lane | Owner |
|------|--------|
| Enablement playbook + scorecard ops | Mira |
| Rituals / calendar / L10 slot | Atlas |
| Ability backlog (telemetry, brief ID field later) | Ava |
| Weekly HubSpot outcome stub | Pulse |
| Accept/Kill brief items; rock approval | Rachel |
| Paid + ops execution of brief | John |
| **Engage** | TBD — not in Grok Bot roster |

---

## 7. First 30 days (suggested)

1. Dan approves this model (edit freely).  
2. Pulse ships UTM convention + weekly MQL stub.  
3. Mira ships 1-page “How to use CMO + Copywriter” for John/Rachel (Dan confirms before send).  
4. Atlas books Monday Synthesis + Friday close-loop.  
5. Run 4 weeks; scorecard v1 is a Sheet Mira fills from Pulse + brief Accept logs.  
6. Ava tickets: optional HubSpot brief-ID property; agent usage telemetry if Ability exposes it.

---

## 8. Open questions for Dan

1. Confirm names/roles: Rachel Glaittli = Growth & Marketing Strategy Lead; John Keever = ? (paid/ops).  
2. Who is **Engage**?  
3. OK to create the enablement 1-pager + scorecard Sheet as drafts on your Drive (not shared to John/Rachel Glaittli you say)?  
4. Weighting: more emphasis on MQL/SQL or on WealthScore completes upstream?
