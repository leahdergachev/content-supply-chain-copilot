---
id: CSC-EXAMPLE
title: Auto-Summaries GA — customer product update email
brand: client (Meridian — fictional company for this example)
content_type: product-update-email
channel: Email to workspace admins (+ in-app changelog snippet)
requested: 2026-07-29
due: 2026-08-06
stage: approval
approval: awaiting-approval
next_action: "Owner: confirm the beta-quote consent (§4), then approve or request changes (§6)"
---

# 0. Request (Intake)

**Raw request (verbatim):**

> "Auto-Summaries goes GA next Thursday. Customers need an email — all workspace admins. Not salesy, they asked for this thing. Mention the beta feedback somehow."

**Clarified scope:** One announcement email to workspace admins + a short in-app changelog snippet adapted from it. No blog post or social this round.

**Due / time sensitivity:** Must send the morning of GA day (Thu Aug 6). Email needs final approval by Aug 4 to clear the send queue.

---

# 1. Brief

| Field | Answer |
|---|---|
| Audience | Workspace admins — the people who can flip the feature on; busy, feature-fatigued, skim on mobile |
| Single message | Auto-Summaries is now available to every workspace — admins can turn it on today in Settings |
| Angle / hook | "The thing you asked for in beta is here" — requested feature delivered, not a sales pitch |
| CTA | Turn on Auto-Summaries in Settings → Features (one link, one action) |
| Success metric | Feature enablement rate (see §7) |
| Voice sources | Meridian product-comms style: plain, direct, no exclamation points, admin-respectful |
| Constraints | Under 200 words; must state summaries are AI-generated; feature is off by default (admin opt-in) |

---

# 2. Draft

**Subject:** Auto-Summaries is ready for your workspace

**Preview text:** The most-requested beta feature is now available to everyone — off by default, on in one click.

---

Hi {first_name},

Auto-Summaries — the most-requested feature from our beta program — is now available to every Meridian workspace.

Turn it on, and every recorded meeting gets an AI-generated summary within minutes: decisions, action items, and who owns what. Beta teams told us it replaced the meeting-notes doc entirely; one program lead reported saving around three hours a week. *(claim pending substantiation — see §4)*

A few things you control:

- **Off by default.** Nothing changes until you enable it in **Settings → Features**.
- **Summaries are AI-generated** and labeled as such — editable before sharing.
- **Your data stays yours.** Summaries are generated in your workspace and are never used to train models.

**[Turn on Auto-Summaries →]**

Questions? Reply to this email — it reaches the product team directly.

— The Meridian Team

---

**In-app changelog snippet (~40 words):**

> **New: Auto-Summaries (GA).** AI-generated meeting summaries with decisions and action items — off by default, enable in Settings → Features. The most-requested feature from beta. Summaries are labeled as AI-generated and editable before sharing.

---

# 3. Review Checklist

- [x] **On-brief** — one feature, one action; resisted adding the roadmap teaser
- [x] **Right register** — product-comms plain style; respectful of admin control, zero hype
- [x] **Hook** — subject leads with the feature name admins already know from beta
- [x] **CTA present and singular** — one button, one settings path
- [x] **Proper nouns verified** — "Auto-Summaries" matches the in-product feature name exactly
- [ ] **Claims grounded** — "three hours a week" is from one beta survey response; needs the survey source linked or the number softened (see §4)
- [x] **No hype words**
- [x] **Channel-native formatting** — under 200 words, bolded controls, mobile-skimmable
- [x] **Honest edge** — leads with "off by default" instead of burying the opt-in

**Reviewer notes:** Cut a second CTA to the docs — competing links depress the primary action. Docs link lives on the settings page instead.

---

# 4. Compliance Flags

| Check | Status | Note |
|---|---|---|
| FTC disclosure (sponsorship, affiliate, material connection) | ⚪ n/a | First-party product announcement |
| AI-generated content disclosure | ⚪ resolved | Email explicitly states summaries are AI-generated and labeled in-product |
| Claim substantiation (stats, results, testimonials) | 🟡 flag | "~3 hours a week" = single beta survey response. Link the survey data or soften to "beta teams reported significant time savings" |
| IP / image / quote rights | 🟡 flag | "Replaced the meeting-notes doc" paraphrases a named beta customer — written consent not yet on file |
| Client confidentiality / NDA exposure | ⚪ n/a | No customer names used in copy |
| PII / named individuals consented | ⚪ n/a | Merge fields only |
| Platform ToS (email) | ⚪ n/a | Existing-customer transactional/product list; unsubscribe handled by ESP footer |

**Open compliance items:** The two 🟡 flags above — substantiate or soften the time-savings claim, and get the beta-quote consent in writing. Both must be resolved or accepted by the owner before approval.

---

# 5. Localization Notes

**Primary market:** US
**Also reaching:** ~30% of workspaces in EU (DACH-heavy) and UK.

- "GA" is internal jargon — copy already avoids it in favor of "now available to every workspace" ✔
- Date references removed from body so the email survives send-queue slips without edits ✔
- Feature availability is identical in all regions — no region-gated claims to caveat
- German translation queued for the in-app changelog snippet only (email goes out English-first per Meridian's norm); kept sentences short and idiom-free so the DE pass is mechanical
- "Your data stays yours / never used to train models" phrasing reviewed for EU audience — factual, no puffery

---

# 6. Approval Status

| Field | Value |
|---|---|
| Submitted for approval | 2026-07-29 |
| Approver | Owner / VA |
| Decision | awaiting |
| Changes requested | |
| Approved on | |
| Published on / where | |

**The copilot never flips this to approved. Human sign-off only.**

---

# 7. Performance Hypothesis

> **We predict** 25% of weekly-active workspaces **will enable** Auto-Summaries **within** 14 days of the email **because** it was the top-requested beta feature, the email targets the exact person with permission to act, and the CTA deep-links to the toggle.

| Field | Value |
|---|---|
| Primary metric | % of weekly-active workspaces with Auto-Summaries enabled |
| Target | 25% by 2026-08-20 |
| Review date | 2026-08-20 |
| Leading indicator (first 24–48h) | Email CTR to the Settings → Features page |

---

# 8. Post-Publish Actuals

| Field | Value |
|---|---|
| Actual result | *(filled after publishing)* |
| vs. hypothesis | |
| Why (best explanation) | |
| Reusable learning | |
