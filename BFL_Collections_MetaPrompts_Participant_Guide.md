# BFL Collections — M365 Copilot Participant Guide
### Meta Prompts for Customer Interaction Documentation, Account Prioritisation, Collections Reporting & Recovery Strategy

**Programme:** Microsoft Copilot for Collections & Recovery  
**Organisation:** Bajaj Finance Limited  
**Interface:** M365 Copilot Chat (microsoft365.com/chat or Teams)  
**Data period:** Apr–May FY2026-27

---

## How Each Exercise Works — The 3-Step Rhythm

| Step | What You Do | What It Shows |
|------|-------------|----------------|
| **Step 1 — Meta Prompt** | Fill in the template and paste into Copilot Chat | Copilot generates a tailored, role-specific working prompt |
| **Step 2 — Generated Prompt** | Review the prompt Copilot created | See how your context shaped the output |
| **Step 3 — Live Apply** | Attach the Excel file via `/` and run the generated prompt | Copilot produces a real collections insight or summary |

---

## The Meta Prompt Template (used in every stage)

```
Act as a Microsoft Copilot prompt expert.

I am a [YOUR ROLE] at [COMPANY/CONTEXT].
I need to [WHAT YOU WANT TO DO].
My audience is [WHO WILL READ THE OUTPUT].

Write me a detailed, structured Copilot prompt I can use to complete this task.
The prompt should specify: role, task, context, constraints, output format, and tone.
```

---

## RTCFT Quick Reference

Every prompt Copilot generates from the template is structured on RTCFT:

| Element | What It Means | Example (Collections Context) |
|---------|---------------|-------------------------------|
| **R** — Role | Who are you? | "You are a collections officer at Bajaj Finance Limited" |
| **T** — Task | What do you need? | "Summarise this customer call and extract PTP details" |
| **C** — Context | What is the situation? | "This is a 90+ DPD personal loan account — third contact attempt" |
| **F** — Format | How should it look? | "Structured summary: Outcome, PTP Date, Amount, Next Action" |
| **T** — Tone | What register? | "Professional, factual, CRM-ready" |

---

## Stage 1 — Customer Interaction Documentation

**Use case:** Auto-summarising call notes, extracting PTP details, and generating CRM-ready entries from call logs.  
**Sheet to attach:** `Call Interaction Log`

---

### Step 1 — Fill in the Template

```
Act as a Microsoft Copilot prompt expert.

I am a Collections Officer at Bajaj Finance Limited.
I need to summarise customer call interactions and extract structured
documentation — including call outcome, promise-to-pay details, and
next action — for entry into our collections CRM system.
My audience is my collections supervisor and the CRM team.

Write me a detailed, structured Copilot prompt I can use to complete this task.
The prompt should specify: role, task, context, constraints, output format, and tone.
```

---

### Step 2 — Copilot Generates Your Working Prompt

```
You are a Collections Officer at Bajaj Finance Limited documenting
customer interactions for the CRM system.

Task: Review the call log provided and generate a structured CRM entry
for each interaction.

Context: These are outbound collections calls made to overdue customers
across Personal Loan, Home Loan, Gold Loan, Two-Wheeler, and Business
Loan portfolios. Calls may result in PTP confirmation, escalation,
dispute, or no response.

Output format — use these labeled fields for each entry:
- Customer Name & Account ID
- Product & DPD
- Outstanding Amount (₹)
- Call Outcome (PTP Confirmed / Escalated / No Response / Dispute / Partial PTP)
- PTP Date & PTP Amount (if applicable)
- Key Points from the Call (2–3 bullets)
- Actions Taken
- Next Follow-up Date & Method

Tone: Factual, professional, CRM-ready. No filler text.
```

---

### Step 3 — Live Apply (attach `Call Interaction Log` via `/`)

**Paste this prompt with the file attached:**

```
I am attaching our Call Interaction Log for May 2026.

1. For Call ID CL-00101 (Ramesh Patil), generate a structured CRM
   summary using the format above.
2. List all calls where outcome is "Escalated" — include the reason
   and recommended next step for each.
3. Calculate the PTP confirmation rate from this log and flag all
   accounts where PTP follow-up is due within the next 7 days.

Format the output as a supervisor-ready report.
```

---

## Stage 2 — Account Prioritisation

**Use case:** Identifying high-priority overdue accounts for recovery efforts — ranked by DPD, outstanding, and risk score.  
**Sheet to attach:** `Account Priority Matrix`

---

### Step 1 — Fill in the Template

```
Act as a Microsoft Copilot prompt expert.

I am a Collections Team Lead at Bajaj Finance Limited.
I need to prioritise overdue accounts from our collections system
and identify which accounts need immediate recovery action today,
based on DPD bucket, outstanding amount, and risk score.
My audience is my collections team and field officers.

Write me a detailed, structured Copilot prompt I can use to complete this task.
The prompt should specify: role, task, context, constraints, output format, and tone.
```

---

### Step 2 — Copilot Generates Your Working Prompt

```
You are a Collections Team Lead at Bajaj Finance Limited reviewing
the daily account priority matrix for recovery planning.

Task: Analyse the account data provided and generate a prioritised
recovery action list for the collections team and field officers.

Context: Accounts span four DPD tiers — Critical (90+ DPD), High
(61–90 DPD), Medium (31–60 DPD), and Low (1–30 DPD). Risk score is
calculated as DPD × Outstanding. Field visits are pre-assigned for
selected accounts.

Output format:
- Top 5 Critical accounts ranked by risk score with recommended action
- Top 5 High priority accounts where last contact was 7+ days ago
- Summary table: total outstanding exposure by priority tier
- Field visit list: accounts marked "Yes" with suggested visit sequence

Tone: Direct, action-oriented, suitable for a morning team briefing.
```

---

### Step 3 — Live Apply (attach `Account Priority Matrix` via `/`)

**Paste this prompt with the file attached:**

```
I am attaching our Account Priority Matrix as of 31 May 2026.

1. List the top 5 Critical priority accounts ranked by risk score.
   For each, state the recommended immediate action.
2. From High priority accounts, flag those where last contact was
   before 25 May 2026 — these need urgent outreach today.
3. Create a summary table showing total account count and outstanding
   exposure (₹ Cr) for each priority tier.
4. List all accounts where Field Visit = Yes and suggest a sequenced
   visit plan for the field team.

Present as a morning collections action brief.
```

---

## Stage 3 — Collections Reporting

**Use case:** Preparing a monthly collections performance summary for management review.  
**Sheet to attach:** `Collections Performance`

---

### Step 1 — Fill in the Template

```
Act as a Microsoft Copilot prompt expert.

I am a Collections Reporting Analyst at Bajaj Finance Limited.
I need to prepare a monthly collections performance summary covering
efficiency trends, PTP fulfilment, GNPA status, and write-off risk
for the period Oct FY2026-27 to May FY2026-27.
My audience is the senior management team in our monthly review meeting.

Write me a detailed, structured Copilot prompt I can use to complete this task.
The prompt should specify: role, task, context, constraints, output format, and tone.
```

---

### Step 2 — Copilot Generates Your Working Prompt

```
You are a Collections Reporting Analyst at Bajaj Finance Limited
preparing a monthly management review document.

Task: Analyse 8 months of collections performance data and generate
a structured management summary.

Context: Data covers Oct FY2026-27 to May FY2026-27. Key metrics
include Collection Efficiency %, PTP Count and Kept %, Accounts
Escalated, Write-off Risk (₹ Cr), and GNPA %. The GNPA threshold
is 5%.

Output format:
1. Executive Summary (250–300 words) — efficiency trend, May vs April,
   GNPA status, write-off risk movement
2. Month-on-month comparison table (Mar / Apr / May) — Collection
   Efficiency %, PTP Kept %, Escalations, Write-off Risk
3. Three key observations
4. Two recommended management actions for June 2026

Tone: Professional, data-driven, boardroom-ready.
```

---

### Step 3 — Live Apply (attach `Collections Performance` via `/`)

**Paste this prompt with the file attached:**

```
I am attaching the BFL Collections Performance Dashboard for
FY2026-27 (Oct 2025 – May 2026).

Generate the full management summary as described — executive summary,
month-on-month comparison table for Mar/Apr/May, three key
observations, and two June 2026 action recommendations.

Flag: Collection efficiency improved from 68.2% in Oct to 78.4% in
May — confirm this trend and highlight whether the 80% target is
achievable in June based on the trajectory.

Also note: escalations spiked in May (94 vs 41 in April) —
call this out as a risk item requiring management attention.
```

---

## Stage 4 — Recovery Strategy Support

**Use case:** Analysing overdue trends, identifying roll-forward risk, and generating differentiated recovery strategies by customer segment.  
**Sheets to attach:** `Overdue Trend Analysis` + `Recovery Strategy Tracker` (attach both)

---

### Step 1 — Fill in the Template

```
Act as a Microsoft Copilot prompt expert.

I am a Collections Strategy Lead at Bajaj Finance Limited.
I need to analyse overdue portfolio trends — specifically roll-forward
rates between DPD buckets — and recommend differentiated recovery
strategies for each customer segment to reduce roll-forward and
improve recovery in June 2026.
My audience is the senior collections leadership team.

Write me a detailed, structured Copilot prompt I can use to complete this task.
The prompt should specify: role, task, context, constraints, output format, and tone.
```

---

### Step 2 — Copilot Generates Your Working Prompt

```
You are a Collections Strategy Lead at Bajaj Finance Limited conducting
a monthly overdue portfolio review.

Task: Analyse roll-forward rates by product and DPD bucket, evaluate
current recovery strategy performance, and recommend tactical
improvements for June 2026.

Context: Two datasets are provided — Overdue Trend Analysis (DPD bucket
data by product, last 3 months) and Recovery Strategy Tracker (segment-
wise strategy, channel, target vs actual recovery %). Roll-forward rate
measures accounts migrating from a lower to a higher DPD bucket.

Output format:
1. Roll-forward analysis — worst product and trend vs prior month
2. Segments where actual recovery is 5%+ below target — with corrective action
3. Best-practice insight — what is Gold Loan doing right and can it apply elsewhere?
4. Portfolio health summary (150 words) for use as a meeting opening statement

Tone: Analytical, strategic, actionable. Suitable for a leadership review.
```

---

### Step 3 — Live Apply (attach both sheets via `/`)

**Paste this prompt with files attached:**

```
I am attaching our Overdue Trend Analysis and Recovery Strategy
Tracker for May 2026.

1. Which product has the worst roll-forward rate in May? Is it better
   or worse than April? What is the likely cause?
2. Identify segments in the Recovery Strategy Tracker where actual
   recovery is furthest below target. Suggest one specific corrective
   action for each in June 2026.
3. Gold Loan shows 88% recovery — the best in the portfolio. Based on
   the data, what factors explain this? Can any be applied to Business
   Loans where recovery is only 68.9%?
4. Write a 150-word portfolio health summary I can read at the start
   of our monthly strategy review meeting.
```

---

## Stage 5 — Bonus: Outlook Copilot for Collections Follow-Up

**Use case:** Drafting a firm but respectful follow-up email to a customer whose PTP was not fulfilled.  
**No file attachment needed — use Outlook Copilot → Draft with Copilot.**

---

### Step 1 — Fill in the Template

```
Act as a Microsoft Copilot prompt expert.

I am a Collections Officer at Bajaj Finance Limited.
I need to draft a follow-up email to a customer whose Promise to Pay
(PTP) was confirmed but not fulfilled on the agreed date — requesting
immediate payment or a revised commitment.
My audience is the customer (overdue account holder).

Write me a detailed, structured Copilot prompt I can use to complete this task.
The prompt should specify: role, task, context, output format, and tone.
```

---

### Step 2 — Copilot Generates Your Working Prompt

```
You are a Collections Officer at Bajaj Finance Limited drafting a
customer-facing follow-up email for an unfulfilled PTP.

Task: Write a professional email reminding the customer of their missed
payment commitment and requesting immediate action.

Context: The customer had confirmed a specific PTP date and amount,
which has not been received. This is a formal follow-up — the next
step if unresolved is a field visit or legal notice.

Output format:
- Subject line
- Opening: Acknowledge the earlier commitment professionally
- Body: State the agreed PTP date and amount; note non-receipt
- Request: Ask for payment by [revised date] or a new commitment
- Closing: State the consequence of continued non-payment (field visit)
- Sign-off: Collections Team, Bajaj Finance Limited

Tone: Professional, firm, respectful — not threatening or aggressive.
```

---

### Step 3 — Live Apply (in Outlook → Draft with Copilot)

**Paste this prompt:**

```
Draft a follow-up email to Suresh Nair (Account BFL-BL-113402) whose
PTP of ₹40,000 was agreed for 1 June 2026 but has not been received.

Request payment by 5 June 2026 or a revised commitment in writing.
Mention that continued non-payment will necessitate a field visit.

Use the format and tone from the prompt above. Include subject line.
```

---

## All Exercises at a Glance

| Stage | Use Case | Sheet / Tool | Output |
|-------|----------|--------------|--------|
| 1 | Customer Interaction Documentation | Call Interaction Log | Structured CRM summary + PTP tracker |
| 2 | Account Prioritisation | Account Priority Matrix | Ranked action brief by risk score |
| 3 | Collections Reporting | Collections Performance | Management executive summary |
| 4 | Recovery Strategy Support | Overdue Trend + Strategy Tracker | Segment-wise recovery strategy brief |
| 5 *(Bonus)* | PTP Follow-up Email | Outlook — no file needed | Customer-ready follow-up email |

---

*Bajaj Finance Limited | AI Academy — Collections & Recovery | Microsoft Copilot Training Programme*
