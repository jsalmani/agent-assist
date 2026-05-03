# Setup — Morning Brief

One-time configuration to get the morning brief running. ~10 minutes.

## 1. Install / open Cowork

If you don't already have it: download from [claude.com/cowork](https://claude.com/cowork) and install.

Open the Cowork desktop app.

## 2. Sign in

Sign in with the **same Anthropic account** you use for Claude Code. This keeps everything under one workspace.

## 3. Verify connectors

In Cowork settings → Connectors, confirm both of these are connected and showing a green/active status:

- **Slack** — connected to your work Slack
- **Microsoft 365 (Outlook)** — connected to your work email

You don't need Fireflies — Fireflies notifications already flow into Slack, and Cowork will pick them up via the Slack connector.

If either is disconnected, click through the OAuth flow in Cowork to reconnect.

## 4. Fill in your delivery email

Open [`prompts/morning-brief.md`](prompts/morning-brief.md) and look for the two `[Jason fills in]` placeholders near the bottom (Step 7 — Deliver):

- **Email from:** your preferred sending address
- **Email to:** your work email (where you want the brief delivered)

Save the file.

## 5. Create the recurring Cowork task

In Cowork, create a new task:

- **Name:** Morning Brief
- **Schedule:** Recurring, Mon–Fri, 8:30am Eastern
- **Prompt:** open `prompts/morning-brief.md`, copy the **entire contents**, paste into the Cowork task prompt field

Save the task.

## 6. First-run test

Manually trigger the task once today (any time — there's a "Run now" button on the task in Cowork). This verifies:

- Connectors are reading correctly
- The brief lands in Slack DM and email
- A markdown file appears at `output/briefings/YYYY-MM-DD.md`

## 7. Review and tune

Read the brief. For anything the agent got wrong:

- Over-flagged something? → add a skip pattern to [`config/skip-patterns.md`](config/skip-patterns.md)
- Missed something important? → add a dated note to [`config/feedback-log.md`](config/feedback-log.md)
- New priority client? → add to [`config/priority-clients.md`](config/priority-clients.md)

The agent reads all four config files at the start of every run, so changes take effect on the next morning brief — no redeployment.

## 8. From here on

Every weekday at 8:30am Eastern, automatically, you'll get:

- 📨 A **Slack DM** from the Cowork bot containing the brief (markdown formatted)
- 📧 An **email** to your delivery address (HTML formatted, same content)
- 💾 A local **markdown file** saved at `~/Code/agent-assist/output/briefings/YYYY-MM-DD.md`

Drafts in the brief are **drafts only** — the agent won't send anything on your behalf. You read, decide, and send manually.

## Troubleshooting

**Brief didn't arrive.** Check the Cowork app — failed runs show in the task history. Most common cause: a connector silently disconnected. Reconnect and re-run.

**Brief arrived but is empty.** Check the time window — if you have no inbound email or Slack activity in the last 24 hrs (or 72 hrs on Mondays), an empty brief is correct. The agent should still produce a "nothing pressing today" note rather than a blank message; if it doesn't, add that as feedback.

**Drafts sound off.** Add 1–2 more recent emails to [`config/tone-samples.md`](config/tone-samples.md). The agent biases toward whatever samples are present.
