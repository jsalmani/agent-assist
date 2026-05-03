# Skip patterns

Email types and patterns the agent should **skip entirely** — not surface in the brief, not even in the FYI section.

The agent reads this file at the start of every run. Add patterns here as you notice the agent over-flagging.

---

## Default skip categories

- **Calendar invites and meeting confirmations** — these belong on the calendar, not the brief
- **Newsletter subscriptions** — anything with an "unsubscribe" footer
- **Marketing email** — CRM notifications, Salesforce alerts, marketing automation, drip campaigns
- **Automated system reports** — build status, monitoring alerts, deployment notifications, uptime pings
- **Mass internal announcements** — HR-wide emails, all-hands recap emails, company newsletters
- **Recruiter outreach** — inbound recruiter pitches (LinkedIn, cold outreach)
- **"Out of office" auto-replies** — vacation responders, OOO bounces
- **Receipts and order confirmations** — Amazon, expense receipts, SaaS billing emails
- **Empty content** — emails where the body is just a signature, thread quote, or forwarded chain with no new content

---

## User-added skip patterns

Add patterns here as you learn the agent is over-flagging. Format flexibly — exact addresses, domains, subject patterns, or short prose rules all work. Be specific about *why* so future-you remembers.

<!-- Examples (delete and replace with real ones over time):
- Skip emails from sender@example.com — automated CRM digest, never needs action
- Skip subject lines starting with "[NOTIFICATION]" — system noise from internal tool
- Skip threads where only Jason's manager is asking and Jason is CC'd — manager handles directly
-->
