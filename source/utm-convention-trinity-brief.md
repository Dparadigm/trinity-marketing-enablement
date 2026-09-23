# UTM convention — Trinity Synthesis Brief attribution
**Owner:** Mira (stamps / enforces on brief-driven pushes) · **Consumer:** Pulse (weekly HubSpot stub)  
**Agreed direction:** Mira + Pulse · **Status:** Draft for Dan · **Date:** 2026-09-23  
**Why:** HubSpot cannot tag contacts to a Trinity brief ID today. UTMs are the no-schema-change bridge.

---

## Goal
Attribute MQLs + speed-to-lead / SLA to Synthesis Brief–driven work **without** a new HubSpot property.

---

## Required parameters

| Param | Pattern / values | Required? |
|-------|------------------|-----------|
| `utm_campaign` | `trinity_brief_<slug>` | **Yes** on every brief-driven push |
| `utm_source` | `meta` · `google` · `linkedin` · `email` · `website` · `youtube` · `organic_social` · `other` | **Yes** |
| `utm_medium` | `paid` · `paid_social` · `ppc` · `cpc` · `organic` · `email` · `nurture` · `enablement` · `social` | **Yes** |
| `utm_content` | Short creative / variant id (`hook-a`, `lead_investing-interest`, `v1`) | Strongly recommended |
| `utm_term` | Keyword (Google Search only) | Optional |

Keep `primary_lead_source__c` aligned with channel (e.g. Meta - Paid Social). UTM = brief key; primary source = channel label.

---

## Slug rules

1. Start from the **Accepted brief item title** (not the Monday pack filename).  
2. Lowercase ASCII only.  
3. Replace spaces / punctuation with `-` (kebab-case); collapse repeats.  
4. Optionally drop stop words (`a`, `the`, `and`, `for`, `to`) if length is tight.  
5. Max ~40 chars after `trinity_brief_` (truncate at a word boundary).  
6. **Stable for the life of that Accept** — do not rename mid-flight or after Pulse has counted that week.  
7. One slug ↔ one logical brief item. Never recycle a slug for a different item later.

| Brief item title | `utm_campaign` |
|------------------|----------------|
| Infinite Banking Investing Interest | `trinity_brief_infinite-banking-investing` |
| Cap Infinite & BYOB Search | `trinity_brief_cap-infinite-byob-search` |
| Whole Life vs Term Q4 | `trinity_brief_whole-life-vs-term-q4` |
| Lead-stage backlog reactivation | `trinity_brief_lead-stage-reactivation` |
| Contact Us / Pages push | `trinity_brief_contact-us-pages` |

---

## Channel examples (copy-paste)

### Meta (paid social)
```
utm_source=meta
utm_medium=paid_social
utm_campaign=trinity_brief_infinite-banking-investing
utm_content=lead_investing-interest
```
URL: `?utm_source=meta&utm_medium=paid_social&utm_campaign=trinity_brief_infinite-banking-investing&utm_content=lead_investing-interest`

### Google Ads (Search / PPC)
```
utm_source=google
utm_medium=ppc
utm_campaign=trinity_brief_cap-infinite-byob-search
utm_content=exact_byob
utm_term={keyword}
```

### Email (newsletter / nurture)
```
utm_source=email
utm_medium=email
utm_campaign=trinity_brief_contact-us-pages
utm_content=2026-09-newsletter-cta
```

### Organic social (Metricool / native)
```
utm_source=organic_social
utm_medium=social
utm_campaign=trinity_brief_infinite-banking-investing
utm_content=ig_carousel_v1
```
Use `linkedin` / `youtube` as `utm_source` when you need network-level breakout; keep `utm_campaign` on the brief slug either way.

### Sales / SDR enablement link (if used)
```
utm_source=website
utm_medium=enablement
utm_campaign=trinity_brief_<slug>
utm_content=sdr_one-pager
```

**Full URL example:**  
`https://paradigmlife.net/4321/?utm_source=meta&utm_medium=paid&utm_campaign=trinity_brief_avalaunch-4321&utm_content=wealthscore-cta`

---

## Who stamps what

| Channel | Who adds UTMs |
|---------|----------------|
| Meta / Google ads | John (or whoever edits Ads Manager) **before** launch |
| Email | Whoever builds the send (ESP UTM fields) |
| Organic social / Metricool | John at schedule time |
| Landing pages / QR | Rachel or John when the item is Accepted |

---

## What NOT to do

- Don’t ship a brief-driven push with blank `utm_campaign`.  
- Don’t use vague campaigns: `trinity`, `cmo`, `test`, `rachel`, `boost`, date-only strings.  
- Don’t reuse one slug for unrelated brief items.  
- Don’t put PII, contact IDs, ticket IDs, or Slack links in UTM values.  
- Don’t change the slug after the first live creative / after Pulse has started counting that week.  
- Don’t invent a new HubSpot property for brief ID in v1 (Ability backlog later).  
- Don’t treat sequence EMAIL/SMS opens as speed-to-lead — Pulse measures first **CALL** only.  
- Don’t mix two brief items under one `utm_campaign`.  
- Don’t use spaces or uppercase in any UTM value.

---

## How Pulse reports weekly (`trinity_brief_*`)

**Cadence:** Monday morning (prior Mon–Sun America/Denver), or on request.  
**Universe:** Contacts with `lifecyclestage = marketingqualifiedlead` and `hs_v2_date_entered_marketingqualifiedlead` in-week.

**Brief-assisted layer** = `utm_campaign` **starts with** `trinity_brief_`.

Pulse weekly stub includes:
1. MQL count + High vs Standard intent (all + brief-assisted).  
2. Breakout by `utm_campaign` slug (+ optional `utm_source` / `utm_medium` / `utm_content`).  
3. First-CALL contact rate + p50 hours-to-CALL (all vs brief-assisted).  
4. SLA hit vs slip (High = 4 biz hrs MT 8am–5pm weekdays; Standard = 24 clock hrs).  
5. SDR split (`assigned_sd_rep`; generic HubSpot owner 90553486 → unassigned).

Contacts with blank / non-`trinity_brief_*` UTM stay in the overall MQL book but **not** in the brief-assisted scorecard layer.

**Stub template on box:** `/workspace/weekly-mql-outcomes-stub.md` · feeds scorecard Section C.

---

## Later upgrade (Ava / Ability — not blocking)
Optional HubSpot property `trinity_brief_id` for offline/influenced touches. UTM convention ships first.
