# AI Content Supply Chain Copilot

A workflow tool that takes any campaign or content request through a seven-stage supply chain: **Brief → Draft → Review Checklist → Compliance Flags → Localization Notes → Approval Status → Performance Hypothesis.**

Every request is one markdown file that travels through the stages. The file *is* the record — no separate tracker to keep in sync. Claude Code is the engine; this repo is the tool.

## Install

1. Clone this repo to `~/content-supply-chain-copilot` (the agent definition uses that path).
2. Deploy the agent so Claude Code can run it:
   ```bash
   cp ~/content-supply-chain-copilot/agent/content-supply-chain.md ~/.claude/agents/
   ```
3. In any Claude Code session, say: **"Run the content supply chain on: [your request]"**

## How it works

1. **Give the copilot a request.** Anything from "LinkedIn post about the workshop" to a full campaign ask.
2. **It creates one pipeline file** in `pipeline/` from `templates/request.md`, assigns an ID (`CSC-001`, `CSC-002`, …), and works the stages in order.
3. **It stops at Approval.** Nothing ships without human sign-off. The agent sets approval to `awaiting-leah` and reports back with exactly what needs a decision.
4. **After you ship it**, tell the copilot the actuals and it closes the loop against the performance hypothesis in section 8.

## The stages

| Stage | What happens |
|---|---|
| 0. Intake | Raw request captured verbatim; brand, channel, and due date pinned down |
| 1. Brief | Audience, single message, angle, CTA, success metric — before any drafting |
| 2. Draft | Channel-native draft(s) in the right brand voice |
| 3. Review Checklist | On-brief, voice, hook, verified proper nouns, no hype words, brand boundary |
| 4. Compliance Flags | FTC/AI disclosure, claim substantiation, IP/image rights, confidentiality, PII |
| 5. Localization Notes | Market fit, idioms that don't travel, date/currency/spelling, or explicit N/A |
| 6. Approval Status | `awaiting-leah` → human flips to `approved` or `changes-requested` |
| 7. Performance Hypothesis | Predicted metric + mechanism + review date, then actuals after shipping |

## Pipeline at a glance

```bash
grep -H "^stage:\|^title:" pipeline/*.md
```

Or ask the copilot: "What's in the content pipeline?"

## Repo structure

```
README.md                       — this file
agent/content-supply-chain.md   — the Claude Code agent that runs the workflow
templates/request.md            — the stage template every request starts from
pipeline/                       — active + shipped requests, one file each
```

## Rules

- **Draft-only.** The copilot never publishes, sends, or schedules. Approval is a human action, recorded in §6 of the request file.
- **Brand boundary.** Austley = leader register. The Marcomm Grind = practitioner/community register. Personal = Leah's thought-leadership voice. The review stage checks the draft landed on the right side.
- **No invented facts.** Stats, quotes, and product claims are verified or cut — flagged in Compliance if unverifiable.
- **Falsifiable hypotheses.** Every request predicts a metric, target, window, and mechanism before it ships — and records actuals after.

## Privacy note

`pipeline/` accumulates real drafts and campaign details over time. Keep this repo **private**. To share the tool publicly as an asset, publish a copy with `pipeline/` emptied (keep the `CSC-EXAMPLE` file) and any private doc IDs scrubbed from the agent definition.
