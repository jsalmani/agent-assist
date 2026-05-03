# agent-assist

Personal productivity agents for Jason, driven by [Cowork](https://claude.com/cowork) (Anthropic's desktop agent app).

This repo isn't code — it's the **prompt, config, and feedback** that power a small set of agents that read Jason's email and Slack and do useful work in the background. The agents themselves run inside Cowork on a schedule.

## How it's organized

```
config/      → the signal: who matters, how Jason sounds, what to ignore
prompts/     → the brain: long, structured prompts pasted into Cowork tasks
output/      → daily briefings, saved locally (gitignored)
```

The flow:

**config drives the prompt → the prompt drives Cowork → Cowork delivers via Slack + email → output saved locally**

## Agents

### morning-brief (live)

Runs Mon–Fri at 8:30am Eastern. Reads Outlook + Slack, surfaces what needs Jason's attention, drafts replies in his voice, and delivers to Slack DM + email. On Mondays it looks back 72 hours; other weekdays, 24 hours.

Prompt: [`prompts/morning-brief.md`](prompts/morning-brief.md)

### Adding more agents

Drop a new prompt at `prompts/<agent-name>.md` and create a matching Cowork task. The same `config/` files get reused unless the new agent needs its own context.

## Updating priority clients

No code change. Just edit [`config/priority-clients.md`](config/priority-clients.md). The next morning brief picks it up automatically.

## Giving the agent feedback

After each morning brief, if the agent over-flagged or missed something, append a dated note to [`config/feedback-log.md`](config/feedback-log.md). The prompt instructs the agent to read this file at the start of every run, so corrections stick — no re-prompting needed.

Same for skip patterns: edit [`config/skip-patterns.md`](config/skip-patterns.md) when the agent surfaces something that should always be skipped.

## ⚠️ This repo is private and stays private

It contains:
- Real client email domains
- Tone samples taken from real customer-facing emails
- Over time, a feedback log that may reference internal projects and people

**Never make this repo public. Never share without redaction.** Daily briefings are gitignored for the same reason.
