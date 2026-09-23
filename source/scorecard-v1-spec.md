> **CORRECTION (Ava 2026-09-23):** Targets = `cmo` + `copywriter` only. No invented session telemetry — proxy via opens/Accepts/draft reviews until Ability usage-export exists.

# Scorecard v1 — Spec (John & Rachel / Trinity marketing)
**Owner:** Mira (fills Sheet from Pulse + Accept logs)  
**Audience:** Dan → then John/Rachel  
**Status:** Draft · **Date:** 2026-09-23  
**Principle:** Weight **outcomes (C) + brief impact (B)** over **usage (A)**. Usage without outcome movement = coaching signal, not a win.

**Outcome ladder:** L1 spend efficiency → L2 traffic/conversion → L3 MQL volume/quality → L4 speed-to-lead/SLA → L5 MQL→SQL → L6 pipeline/closed.

**CSV seed:** `scorecard-v1-template.csv` (import → Google Sheet tabs).

---

## 1. Artifact shape

| Item | Recommendation |
|------|----------------|
| Form | Google Sheet (one workbook) |
| Cadence | **Weekly** row per person × week (Mon–Sun America/Denver) |
| Fill deadline | Monday EOD MT for prior week |
| Who fills | **Mira** primary; Pulse drops HubSpot numbers; Rachel/John confirm Accept log + D/E monthly |
| Review | Marketing Monday L10 (5 min) + monthly deep-dive |

---

## 2. Tabs

| Tab | Purpose | Maps to |
|-----|---------|---------|
| `Weekly_Score` | One row per person per week; A–C scored + rollups | A B C |
| `Accept_Log` / `Brief_Log` | Item-level Accept/Defer/Kill from Synthesis Brief | B (+ feeds A) |
| `Pulse_MQL` | Paste/import of Pulse weekly stub | C |
| `UTM_Hygiene` | Brief-driven pushes vs correct `trinity_brief_*` stamp | E |
| `Monthly_DE` | Purpose sentences + improve-the-machine | D E |
| `Definitions` | Locked metric defs, SLA clocks, weights | — |

---

## 3. Section A — Usage & collaboration (leading) · weight **15%**

| Column | Who fills | Definition |
|--------|-----------|------------|
| `brief_opened` | Honor / Mira | Y/N — Synthesis Brief opened Monday |
| `accepted_count` | Accept_Log | Count of Accepts for that person+week |
| `one_thing_done_by_wed` | Rachel/John → Mira | Y / N / Partial |
| `cw_briefs_started` | Mira | Copywriter briefs kicked for Accepted items |
| `cw_drafts_reviewed` | Mira / owner | Drafts human-reviewed (Approval Queue) |
| `cw_assets_live` | Owner | Assets live this week |
| `cw_cycle_days_p50` | Mira | Median days brief→live (blank if n<2) |
| `agent_sessions_logged` | Honor | Light count until Ability telemetry |

**A_norm (0–100, conceptual):** average of normalized leading signals (opened, One Thing, % drafts live of started, capped session score). Cap contribution at 15% of total — never green the week on A alone.

---

## 4. Section B — Brief impact (leading → lagging) · weight **35%**

| Column | Who fills | Definition |
|--------|-----------|------------|
| `accepted_with_metric` | Accept_Log | Accepts with non-blank test metric |
| `pct_accepted_with_metric` | Sheet | `accepted_with_metric / accepted_count` |
| `completed_in_window` | Accept_Log | Accepts marked shipped by Friday |
| `pct_completed_in_window` | Sheet | `completed_in_window / accepted_count` |
| `carryover_count` | Accept_Log | Still open >0 weeks |
| `stale_carryover_ge_2w` | Accept_Log | Age ≥ 2 weeks (**penalty**) |
| `kills_with_reason` | Accept_Log | Kill rows with why (hygiene bonus) |

**B_norm (conceptual):**
```
B = 0.4*(pct_accepted_with_metric*100)
  + 0.4*(pct_completed_in_window*100)
  - 10*stale_carryover_ge_2w
  + 5*min(kills_with_reason, 3)
B = MAX(0, MIN(100, B))
```

### Accept_Log columns
`week_start` · `brief_date` · `rank` (0=THE ONE THING) · `item_title` · `slug` · `decision` (Accept/Defer/Kill) · `owner` · `why` · `projected_outcome` · `outcome_tier` (L1–L6) · `test_metric` · `due_day` · `shipped` · `metric_moved` · `utm_stamped` · `carryover_weeks` · `friday_note` · `copywriter_used`

---

## 5. Section C — Funnel outcomes (Pulse weekly stub) · weight **40%**

Paste from Pulse; optional person attribution only where lane-clear (else team context columns).

| Column | Source | Notes |
|--------|--------|-------|
| `mql_entered` | Pulse | Week universe |
| `mql_high` / `mql_standard` | Pulse | Intent split |
| `mql_brief_assisted` | Pulse | `utm_campaign` starts with `trinity_brief_` |
| `first_call_rate_all` | Pulse | First **CALL** only (COMPLETED/NO_ANSWER/BUSY) |
| `first_call_rate_brief` | Pulse | Brief-assisted subset |
| `p50_hrs_to_call_all` / `_brief` | Pulse | Hours |
| `sla_hit_pct_high` | Pulse | High = 4 biz hrs MT |
| `sla_hit_pct_standard` | Pulse | Standard = 24 clock hrs |
| `sla_new_slips` | Pulse | Count |
| `sdr_unassigned_pct` | Pulse | Blank / generic owner 90553486 |

**C_norm (conceptual):** blend of (a) High Intent share vs prior 4-wk avg, (b) brief first-CALL rate vs all (brief should not lag), (c) inverted p50 hours-to-CALL, (d) SLA hit %, (e) penalty if `sdr_unassigned_pct` > 10%. WoW / baseline direction beats raw volume vanity.

---

## 6. Section D — Purpose / intention (qualitative) · weight **5%** (monthly, viewable weekly)

| Column | Who fills | Definition |
|--------|-----------|------------|
| `purpose_sentence` | Rachel / John | “This week the brief existed to ___ so that ___.” Tied to L1–L6 |

Scored lightly monthly; paste onto nearest weekly rows for visibility.

---

## 7. Section E — Improve the machine (monthly) · weight **5%**

| Column | Who fills | Definition |
|--------|-----------|------------|
| `wrong_or_unactionable_recs` | Rachel / John | Count + themes from Kills / bad briefs |
| `feedback_to_ava` | Mira | Ability tickets filed — **do not clone** CMO/copywriter agents |
| `utm_hygiene_pct` | Mira / UTM_Hygiene | `% brief-driven pushes correctly tagged trinity_brief_*` |

---

## 8. Total score (conceptual)

```
Total = 0.15*A_norm + 0.35*B_norm + 0.40*C_norm + 0.05*D_norm + 0.05*E_norm
RAG: Green ≥70 · Amber 50–69 · Red <50
```

**Alternate simple v1 (if Sheet stays thin):** Outcomes 50 / Brief impact 30 / Usage 20 — still **never** green on usage alone if B+C flat/down.

Coach on usage-without-outcomes; celebrate outcomes-with-light-usage.

---

## 9. Who fills what (RACI-lite)

| Input | Rachel | John | Mira | Pulse | Atlas | Ava |
|-------|--------|------|------|-------|-------|-----|
| Accept/Defer/Kill Monday | A | C | I | — | Facilitates slot | — |
| Friday close-loop | A (strategy) | A (paid) | C | — | — | — |
| Pulse stub numbers | I | I | C (paste) | **A** | — | — |
| Sheet math / RAG | I | I | **A** | I | I | — |
| Monthly D/E sentences | A | A | C | — | — | I (tickets) |
| Ability feedback tickets | C | C | C | — | — | **A** backlog |

A=accountable · C=contributes · I=informed

---

## 10. Weekly cadence

| Day | Action |
|-----|--------|
| Mon AM | Pulse posts prior-week MQL stub; Mira pastes `Pulse_MQL` |
| Mon L10 | Rachel/John Accept log; Mira starts week row |
| Wed | Check THE ONE THING status |
| Fri | Close-loop on Accepts; UTM hygiene spot-check |
| Next Mon EOD | Mira locks `Weekly_Score` totals |

---

## 11. Out of scope for v1

- Full MQL→SQL→close revenue attribution (needs deal props — Ability later).  
- Automatic agent-session telemetry (honor system until Ability exposes it).  
- HubSpot native brief-ID property (UTM bridge only).  
- Sharing Sheet to John/Rachel until Dan confirms.  
- Messaging John/Rachel/Tyler/Mark/Ability (Dan gate).

---

## 12. Success criteria (first 4 weeks)

1. Every Monday has Accept log for top items + THE ONE THING.  
2. ≥80% of traffic-creating Accepts have `trinity_brief_*` stamp.  
3. Pulse stub lands weekly without PII dumps.  
4. Scorecard total moves when B+C move — not when only sessions are logged.

---

## v1.2 addendum (2026-09-23 — Atlas + Pulse + Ava)

### Name lock
Rachel **Glaittli** (rglaittli@) · John **Keever**

### Synthesis execution metrics (Brief_Log)
- items_claimed
- time_to_first_draft_hrs
- time_to_published_hrs  (failure mode: brief done / page not live)
- reopen_rate

### Outcomes source
Pulse weekly MQL stub (`trinity_brief_*`); numbers through Gauge + Pulse — no second analytics path.

### Cadence (propose only)
Prefer async Monday Slack after Synthesis; optional biweekly 15 min on John’s Thu 1:30–2:00 MT. Atlas holds invites until Dan confirms.
