# Trinity CMO brief → HubSpot UTM convention

**Owner:** Mira (stamps on brief-driven pushes)  
**Consumer:** Pulse (attributes weekly MQL / speed-to-lead)  
**Rule:** Every brief-driven push that can create or re-enter an MQL must carry these UTMs so HubSpot `utm_*` fields can be joined to the brief.

## Required fields

| Field | Pattern | Rules |
|-------|---------|--------|
| `utm_campaign` | `trinity_brief_<slug>` | **Required.** `<slug>` = kebab-case from brief title, max ~40 chars, ASCII only. Stable for the life of that brief (do not rename mid-flight). |
| `utm_source` | Platform of the click/land | `meta` \| `google` \| `linkedin` \| `email` \| `website` \| `youtube` \| `other` |
| `utm_medium` | How the traffic was bought/sent | `paid` \| `organic` \| `email` \| `nurture` \| `enablement` \| `ppc` \| `paid_social` |
| `utm_content` | Optional creative / variant | Short id: creative name, ad set, email module, or `v1`/`v2`. Use `_` not spaces. |

## Slug examples

| Brief title | `utm_campaign` |
|-------------|----------------|
| Infinite Banking Investing Interest | `trinity_brief_infinite-banking-investing` |
| Whole Life vs Term Q4 | `trinity_brief_whole-life-vs-term-q4` |
| Contact Us / Pages push | `trinity_brief_contact-us-pages` |

## Examples Mira can stamp

**Meta paid (typical PLI):**  
`utm_source=meta` · `utm_medium=paid` · `utm_campaign=trinity_brief_infinite-banking-investing` · `utm_content=lead_investing-interest`

**Google PPC:**  
`utm_source=google` · `utm_medium=ppc` · `utm_campaign=trinity_brief_whole-life` · `utm_content=exact_whole-life`

**Email / newsletter enablement:**  
`utm_source=email` · `utm_medium=email` · `utm_campaign=trinity_brief_<slug>` · `utm_content=2026-newsletter` (or module name)

**Sales / SDR enablement link (if used):**  
`utm_source=website` · `utm_medium=enablement` · `utm_campaign=trinity_brief_<slug>` · `utm_content=sdr_one-pager`

## Do / don’t

- **Do** put the same `utm_campaign` on every creative for that brief so Pulse can roll up one row per brief.
- **Do** keep `primary_lead_source__c` aligned with channel (e.g. Meta - Paid Social) — UTM is the brief key; primary source is the channel label.
- **Don’t** reuse a slug for a different brief later.
- **Don’t** put PII or internal ticket ids in UTM values.
- **Don’t** rely on sequence/email opens for speed-to-lead; Pulse still measures first **CALL** only.

## How Pulse will attribute

Weekly: MQLs with `hs_v2_date_entered_marketingqualifiedlead` in the week where `utm_campaign` starts with `trinity_brief_` → count, intent, first-CALL rate, p50 hours-to-CALL, SLA hit/slip, SDR split — by brief slug (and optional `utm_content` breakout).

Contacts with blank UTM stay in the overall MQL book but **not** in the “brief-assisted” scorecard layer.
