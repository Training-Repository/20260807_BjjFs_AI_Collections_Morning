# Meta-Prompting Guide — Collections & Recovery
**Microsoft Copilot Training | Bajaj Finance Limited**

---

## What Is Meta-Prompting?

Instead of writing a prompt yourself, you ask Copilot to write the prompt for you — by telling it your role, your task, and what you need.

You are essentially saying:

> *"You are a prompt expert. You know how to talk to AI. Write me a prompt I can use for my actual work."*

The output becomes your **reference prompt** — something you refine and reuse across different Collections workflows and recovery reporting situations.

---

## The Core Meta-Prompt Formula

```
Act as a Microsoft Copilot prompt expert.
I am a [YOUR ROLE] at [COMPANY/CONTEXT].
I need to [WHAT YOU WANT TO DO].
My audience is [WHO WILL READ THE OUTPUT].
Write me a detailed, structured Copilot prompt I can use to complete this task.
The prompt should specify: role, task, context, constraints, output format, and tone.
```

---

## Meta-Prompts for Collections — Bajaj Finance

Use these as your starting point. Copy, paste, and run in Copilot. Use the output as your working prompt for your exercises.

---

### 1. Customer Interaction Documentation

```
Act as a Microsoft Copilot prompt expert.
I am a Collections Officer at Bajaj Finance Limited, an NBFC. I make outbound calls to
overdue customers across Personal Loan, Home Loan, Gold Loan, Two-Wheeler, and Business
Loan portfolios. After each call, I need to document the interaction in our CRM — capturing
the call outcome, promise-to-pay details, actions taken, and the next follow-up step.

My audience is my collections supervisor and the CRM team who use this data for daily
recovery tracking and escalation decisions.

Write me a detailed, structured Copilot prompt I can use to produce a CRM-ready call
summary from my interaction notes. The prompt should specify: my role, the task, what
input I will provide, the exact output format for each field (outcome, PTP date, PTP amount,
actions taken, next follow-up), and an appropriate factual and professional tone.
```

---

### 2. Account Prioritisation

```
Act as a Microsoft Copilot prompt expert.
I am a Collections Team Lead at Bajaj Finance Limited. Every morning I review an account
priority matrix covering overdue customers across four DPD tiers — Critical (90+ DPD),
High (61–90 DPD), Medium (31–60 DPD), and Low (1–30 DPD) — with risk scores, outstanding
amounts, last contact dates, and field visit flags. I need to produce a prioritised daily
action list: which accounts to call first, which need field visits today, and where
outstanding exposure is highest.

My audience is my collections team and field officers who use this brief at the start of
each working day.

Write me a Copilot prompt I can use to produce this prioritised action list. The prompt
should tell Copilot exactly how to rank accounts, what to flag (stale contacts, unbooked
field visits, critical exposure), and what tone to use (direct, action-oriented, briefing-ready).
```

---

### 3. Collections Performance Reporting

```
Act as a Microsoft Copilot prompt expert.
I am a Collections Reporting Analyst at Bajaj Finance Limited. I maintain a monthly
performance dashboard covering 8 metrics — Collection Efficiency %, PTP Count, PTP Kept %,
Accounts Escalated, Field Visits, Write-off Risk (₹ Cr), GNPA %, and New Delinquencies —
tracked month-on-month for FY2026-27. I need to produce a management performance summary:
an efficiency trend narrative, a month-on-month comparison for the last 3 months, and
management action recommendations for the next month.

My audience is the senior collections leadership team who use this for their monthly
management review meeting.

Write me a structured Copilot prompt that will produce this collections performance summary
from my dashboard data. The prompt should specify format (executive narrative + comparison
table + action recommendations), tone (professional, data-driven, management-ready), and
what signals to surface (efficiency trajectory, GNPA vs 5% threshold, escalation spikes,
write-off risk movement).
```

---

### 4. Overdue Trend and Recovery Strategy Analysis

```
Act as a Microsoft Copilot prompt expert.
I am a Collections Strategy Lead at Bajaj Finance Limited. I track overdue portfolio trends
monthly across five product categories — Personal Loan, Home Loan, Gold Loan, Two-Wheeler,
and Business Loan — with DPD bucket counts, outstanding amounts, roll-forward rates between
buckets, and recovery rates. I also maintain a Recovery Strategy Tracker with segment-wise
strategies, channels, target vs actual recovery %, and status flags. I need to identify which
segments are underperforming, understand roll-forward patterns, and recommend differentiated
recovery actions for the coming month.

My audience is the senior collections leadership team who will use this for monthly strategy
planning and resource allocation decisions.

Write me a Copilot prompt that will produce this recovery strategy analysis from my two
datasets. The prompt should specify format (roll-forward analysis + underperforming segment
flags + corrective actions + portfolio health summary), tone (analytical, strategic,
actionable), and what patterns to surface (worst roll-forward product, segments where actual
is 5%+ below target, best-practice insights from high-performing products).
```

---

### 5. PTP Follow-Up and Customer Communication

```
Act as a Microsoft Copilot prompt expert.
I am a Collections Officer at Bajaj Finance Limited. I need to draft follow-up emails and
WhatsApp message templates for customers whose Promise to Pay (PTP) was confirmed but not
fulfilled on the agreed date. The communication must reference the specific PTP amount and
date, request immediate payment or a revised commitment, and indicate the consequence of
continued non-payment — without being threatening or aggressive.

My audience is the overdue customer receiving the communication directly.

Write me a Copilot prompt I can use to draft this follow-up communication. The prompt should
specify format (subject line + opening + body + request + consequence + sign-off), tone
(professional, firm, respectful — never threatening), and what details to personalise
(customer name, account ID, PTP date, PTP amount, revised deadline).
```

---

## Still Confused? Run This.

If the prompt Copilot wrote doesn't feel right — too generic, wrong format, wrong tone — don't rewrite it yourself. Use this follow-up prompt instead:

```
The prompt you wrote is a good start, but I need you to adjust it.
Here is what I want to change:

- [Describe what felt off — e.g., "the format doesn't match what my supervisor expects"]
- [Describe what's missing — e.g., "it doesn't tell Copilot to flag accounts with stale contacts"]
- [Describe the tone issue — e.g., "it sounds too formal for a daily team briefing"]

Please rewrite the prompt with these corrections.
Keep the same structure (Role / Task / Context / Format / Tone) but fix the parts I've described.
```

---

## What to Do With the Output

Once Copilot gives you a well-structured prompt:

1. **Read it** — does it reflect your actual Collections role and recovery context?
2. **Replace the placeholders** — swap generic text with your real account data, DPD bucket, or product details.
3. **Run it** — use it on the exercise dataset provided during training.
4. **Save it** — this is your reusable reference prompt for that Collections task type.

---

*Bajaj Finance Limited | AI Academy — Collections & Recovery | Microsoft Copilot Training Programme*
