# Weekly MQL outcomes stub (HubSpot layer)

**For:** John / Rachel scorecard — HubSpot / inbound MQL layer  
**Reporter:** Pulse (read-only)  
**Cadence:** Monday morning (prior Mon–Sun America/Denver), or on request  
**Universe:** Contacts with `lifecyclestage = marketingqualifiedlead` and `hs_v2_date_entered_marketingqualifiedlead` in the report week (not full MQL backlog)

---

## 1. Volume & intent

| Metric | Value | Notes |
|--------|-------|--------|
| MQLs entered (week) | _n_ | Entered MQL stage in-window |
| High Intent | _n_ (_%_) | `inbound_intent_type` = High Intent |
| Standard Intent (incl. blank) | _n_ (_%_) | Standard or blank |

## 2. Source & UTM (brief-assisted)

| primary_lead_source__c | MQLs | Share |
|------------------------|------|-------|
| … | | |

**Brief-assisted** (`utm_campaign` starts with `trinity_brief_`):

| utm_campaign (brief) | utm_source / medium | MQLs | High / Std |
|----------------------|---------------------|------|------------|
| trinity_brief_… | | | |

_Non-brief MQLs (blank or other UTM): _n__

## 3. Speed-to-lead (human CALL only)

**First touch** = first logged **CALL** after MQL enter with disposition COMPLETED, NO_ANSWER, or BUSY. Sequence EMAIL / SMS do **not** count.

| Metric | All MQLs | Brief-assisted only |
|--------|----------|---------------------|
| First-CALL contact rate | _%_ (_n_/_N_) | _%_ |
| p50 hours to first CALL | _h_ | _h_ |
| Still untouched at week end | _n_ | _n_ |

## 4. SLA hit / slip

| Intent | SLA | Hits | New slips | Still open (end of week) |
|--------|-----|------|-----------|---------------------------|
| High | 4 business hrs (8am–5pm MT weekdays; overnight/weekend → next weekday 8am) | | | |
| Standard | 24 clock hours | | | |

Cured this week (had been slipping, got qualifying CALL): _n_

## 5. SDR split (`assigned_sd_rep`)

| Owner | MQLs | First-CALL rate | p50 hrs to CALL | SLA hit % |
|-------|------|-----------------|-----------------|-----------|
| Hallie Hillman | | | | |
| David McKeever | | | | |
| Unassigned | | | | |

(Generic HubSpot owner 90553486 → treat as unassigned.)

## 6. One-line Pulse takeaway

_What moved / what slipped / one source or brief that dominated. No PII dump; name contacts only if Dan asks or an SLA is on fire._

---

### Definitions (locked)

- Clock: America/Denver  
- SLA High = 4 biz hrs; Standard/blank = 24 clock hrs  
- `notes_last_contacted` alone is **not** used (polluted by sequences)  
- Read-only: no emails, sequences, property edits, or owner changes unless Dan confirms  

### Out of this HubSpot stub (other layers)

- Synthesis brief → creative production (Mira)  
- Revenue ladder / pipeline stages (needs deal props + rule — not on Pulse hourly watch yet)  
- WealthScore (add only if property + pass threshold confirmed)  
