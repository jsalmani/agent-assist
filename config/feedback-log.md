# Feedback log

A chronological log Jason maintains. Add a dated section after each morning brief with anything the agent should have done differently.

**The agent reads this file at the start of every run and incorporates the feedback into its filtering and drafting logic.** Entries here override the defaults in `priority-clients.md` and `skip-patterns.md` when there's a conflict.

## Format

After each brief, add a section like:

```
### YYYY-MM-DD feedback
- Skip emails from `someone@somedomain.com` — automated system, not a person
- Always escalate any email mentioning "[Project Name]" — high-priority initiative
- Drafts are sounding too formal — pull more from Sample 3 (casual technical explainer)
```

Keep entries short and specific. Reference the email subject or sender that triggered the correction so future-you (and the agent) understand the context.

---

## Example entry (delete or keep as a format reference)

### 2026-04-28 feedback
- Skip emails from `digest@internal-tool.example.com` — automated weekly digest, never needs action
- Always escalate emails from `priya.example@bcbsma.com` even if just a status update — she's a key champion
- The Tuesday brief over-drafted formal replies; pull more from Sample 1 (casual savings estimation tone) for technical asks

---

## Feedback log

<!-- Add new dated entries below this line, newest at the top -->
