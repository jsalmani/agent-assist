# Priority clients

This file is the **primary triage signal** for the morning brief. The agent uses it to decide what to escalate (🔴 NEEDS ACTION TODAY) versus what to surface lower (🟡 NEEDS REVIEW or ⚪ FYI).

Edit this file directly to update priorities — no redeployment needed. The agent re-reads it on every run.

---

## Priority domains (always escalate)

Any email from these domains is HIGH priority by default:

- `xcelenergy.com` — Xcel Energy
- `bannerhealth.com` — Banner Health
- `ci.com` — CI Investments
- `mcd.com` — McDonald's
- `sunlife.com` — Sun Life
- `pg.com` — Procter & Gamble
- `sutterhealth.org` — Sutter Health
- `gulfstream.com` — Gulfstream
- `bcbsma.com` — Blue Cross Blue Shield of MA

---

## Priority individuals (always escalate, regardless of sending domain)

Specific people who should always be flagged, even if they email from a personal address or a domain not on the priority list above. Use this for executive sponsors, key champions, or partners.

Format: `Name <email@domain> — context`

Example:
- `Jane Doe <jane.doe@example.com> — exec sponsor at Banner Health, sometimes emails from personal`

<!-- Add specific people here as needed -->

---

## Deprioritize / noise (downgrade these)

Senders that look noisy and should be dropped to ⚪ FYI or skipped entirely. Add to this list over time as the agent surfaces things that don't need surfacing.

Seed examples (patterns, not exact addresses):

- `marketing@*`
- `no-reply@*`
- `notifications@*`

<!-- Jason adds known-noise senders here over time. Patterns or full addresses both work. -->
