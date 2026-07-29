# AI Content Supply Chain Copilot

A workflow tool that takes any campaign or content request through a seven-stage supply chain: **Brief → Draft → Review Checklist → Compliance Flags → Localization Notes → Approval Status → Performance Hypothesis.**

Every request is one markdown file that travels through the stages. The file *is* the record — no separate tracker to keep in sync. [Claude Code](https://claude.com/claude-code) is the engine; this repo is the tool.

Built by **Leah Dergachev**, who runs it as part of the content operation behind Austley (AI enablement for marketing & comms teams), The Marcomm Grind community, and her personal brand.

## Install

1. Use this template (green button above) or clone the repo to `~/content-supply-chain-copilot` — the agent definition uses that path.
2. Deploy the agent so Claude Code can run it:
   ```bash
   cp ~/content-supply-chain-copilot/agent/content-supply-chain.md ~/.claude/agents/
   ```
3. In any Claude Code session, say: **"Run the content supply chain on: [your request]"**

## Make it yours

- **Voice calibration:** open `agent/content-supply-chain.md` and replace the voice-docs placeholder with links or paths to your own brand voice and content pillar docs. The better this input, the better the drafts.
- **Brands & registers:** the template supports multi-brand operators (own brands, personal voice, client work — the worked example is a client-brand request). Adapt the `brand:` values in the template to your own.
- **Approval flow:** the template assumes one human approver (you, or you + a VA). The agent can never mark anything approved — that's deliberate. Keep it that way.

## How it works

1. **Give the copilot a request.** Anything from "LinkedIn post about the workshop" to a full campaign ask.
2. **It creates one pipeline file** in `pipeline/` from `templates/request.md`, assigns an ID (`CSC-001`, `CSC-002`, …), and works the stages in order.
3. **It stops at Approval.** Nothing publishes without human sign-off. The agent sets approval to `awaiting-approval` and reports back with exactly what needs a decision.
4. **After you publish it**, tell the copilot the actuals and it closes the loop against the performance hypothesis in section 8.

## The stages

| Stage | What happens |
|---|---|
| 0. Intake | Raw request captured verbatim; brand, channel, and due date pinned down |
| 1. Brief | Audience, single message, angle, CTA, success metric — before any drafting |
| 2. Draft | Channel-native draft(s) in the right brand voice |
| 3. Review Checklist | On-brief, voice, hook, verified proper nouns, no hype words, brand boundary |
| 4. Compliance Flags | FTC/AI disclosure, claim substantiation, IP/image rights, confidentiality, PII |
| 5. Localization Notes | Market fit, idioms that don't travel, date/currency/spelling, or explicit N/A |
| 6. Approval Status | `awaiting-approval` → a human flips to `approved` or `changes-requested` |
| 7. Performance Hypothesis | Predicted metric + mechanism + review date, then actuals after publishing |

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
pipeline/                       — your requests, one file each (see note below)
```

**Your drafts stay local.** `pipeline/` is gitignored (except the worked example), so real requests — unpublished drafts, campaign details, client context — live only on your machine and are never pushed to this repo. See [`pipeline/CSC-EXAMPLE-auto-summaries-product-update.md`](pipeline/CSC-EXAMPLE-auto-summaries-product-update.md) — a product-update email for a fictional SaaS client, shown mid-flight at the approval stage with live compliance flags.

## Rules

- **Draft-only.** The copilot never publishes, sends, or schedules. Approval is a human action, recorded in §6 of the request file.
- **Brand boundary.** Every draft is checked against the register it belongs in — leader vs. practitioner vs. personal voice — so multi-brand operators don't cross streams.
- **No invented facts.** Stats, quotes, and product claims are verified or cut — flagged in Compliance if unverifiable.
- **Falsifiable hypotheses.** Every request predicts a metric, target, window, and mechanism before it produces — and records actuals after.
