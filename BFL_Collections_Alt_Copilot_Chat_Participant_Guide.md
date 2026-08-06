# Copilot Chat for Excel — Participant Exercise Guide
### Formulas & Pivot Tables for Collections
**Bajaj Finance Limited | M365 Copilot Training**
**File:** `BFL_Collections_Copilot_Demo.xlsx`
**Mode:** Copilot Chat (no Microsoft 365 Copilot licence required)

---

## Before You Begin

### What You Need
- **Excel** open with `BFL_Collections_Copilot_Demo.xlsx`
- **Copilot Chat** open in a second window — either:
  - `https://copilot.cloud.microsoft` (M365 Copilot Chat, work account), or
  - The **Copilot** button in Microsoft Edge, or
  - The Copilot app in Windows / Teams
- Both windows side by side (**Win + ←** and **Win + →**) — you will be switching constantly

### How This Session Works
Copilot Chat is **not connected to your workbook.** It cannot insert formulas, build pivot tables, or change anything in Excel. It can *write* everything for you — you paste it in.

Every exercise follows the same **two-step rhythm**:

| Step | Where | What You Do |
|------|-------|-------------|
| **1. Ask** | Copilot Chat | Paste the prompt, get the formula or the steps |
| **2. Apply** | Excel | Paste into the cell, press Enter, fill down |

> **Key habit:** Because Chat cannot see your file, **you** must describe the file. That is the entire skill this session teaches — and it is the same skill that makes every other AI tool work well.

**The sheet:** headers are in **row 2**; data runs **row 3 to row 27** (25 accounts). Columns **N–Q are empty** — you will fill these using Copilot Chat. *(Column M is a deliberate blank spacer — it matters later, in Exercise 6.)*

---

## Step 0 — Set the Context (do this once)

Open Copilot Chat and paste this **first**. Everything after it can be short, because Chat now knows your sheet.

```
I'm working in Excel on a collections tracker. You can't see the file,
so here is the layout:

Headers are in row 2. Data runs from row 3 to row 27 (25 account rows).

A  Account ID          (text, e.g. BFL-PL-001)
B  Customer Name       (text)
C  Product             (Personal Loan, Home Loan, Gold Loan, Two-Wheeler,
                        Business Loan)
D  DPD                 (number — days past due)
E  Outstanding (₹)     (number)
F  EMI Amount (₹)      (number)
G  Call Outcome        (PTP Confirmed, Escalated, No Response, Partial PTP,
                        Dispute, Promise Broken, Callback)
H  PTP Date            (date, blank if there is no promise-to-pay)
I  PTP Amount (₹)      (number, blank if no PTP)
J  Collector Name      (text)
K  Zone                (Pune, Mumbai, Nashik, Nagpur)
L  Field Visit         (Yes / No)
M  (blank spacer — ignore it)
N  DPD Bucket          (empty — I'll add this)
O  Risk Score          (empty — I'll add this)
Q  EMIs Overdue        (empty — I'll add this)

For the rest of this conversation: when I ask for a formula, give me the
formula for the FIRST data row (row 3), ready to paste and fill down.
Give me the formula on its own line, then a one-line explanation. No long
preamble.
```

> **Trainer note:** This single block is the difference between five sharp answers and five vague ones. Keep it visible on screen — participants will refer back to it.

---

## Exercise 1 — DPD Bucket (Column N)

### Step 1 — Ask (Copilot Chat)

```
Write a formula for cell N3 that classifies each account into a DPD bucket
based on DPD (column D):
- "Critical" if DPD is more than 90
- "High" if DPD is 61 to 90
- "Medium" if DPD is 31 to 60
- "Low" if DPD is 30 or less
```

**Expected output:**
```excel
=IF(D3>90,"Critical",IF(D3>60,"High",IF(D3>30,"Medium","Low")))
```

### Step 2 — Apply (Excel)
1. Click **N2** → type `DPD Bucket` → Enter
2. Click **N3** → paste the formula → Enter
3. Select **N3**, double-click the small square at the bottom-right corner of the cell to fill down to **N27**
   *(or select N3:N27 and press **Ctrl + D**)*

> **Try this:** Ask Copilot Chat — *"What does this formula return for a DPD of exactly 90, and exactly 60?"* It will walk the boundaries and confirm 90 lands in **High** (because the first test is `>90`, not `>=90`) and 60 lands in **Medium**. This is the classic off-by-one trap in banded IFs — worth seeing before it bites you on a real report.

> **Bonus prompt:** *"Rewrite this using IFS instead of nested IFs."* Compare the two — which one would you rather hand a colleague to maintain?

---

## Exercise 2 — Risk Score (Column O)

### Step 1 — Ask (Copilot Chat)

```
Write a formula for cell O3 that creates a Risk Score by multiplying DPD
(column D) by the Outstanding amount (column E).
```

**Expected output:**
```excel
=D3*E3
```

### Step 2 — Apply (Excel)
1. **O2** → `Risk Score`
2. **O3** → paste → Enter → fill down to **O27**

> **Try this:** *"My Risk Score numbers are huge and hard to read. Can you scale them to lakhs?"* Chat will suggest dividing by 100000 — a quick lesson in turning a raw score into something an executive can actually read.

---

## Exercise 3 — EMIs Overdue (Column Q)

### Step 1 — Ask (Copilot Chat)

```
Write a formula for cell Q3 that estimates how many EMIs are overdue, by
dividing the Outstanding amount (column E) by the EMI Amount (column F) and
rounding to the nearest whole number.
```

**Expected output:**
```excel
=ROUND(E3/F3,0)
```

### Step 2 — Apply (Excel)
1. **Q2** → `EMIs Overdue`
2. **Q3** → paste → Enter → fill down to **Q27**

> **On your own data:** in this training file every account has an EMI Amount, so the formula never errors. On a live tracker, some rows have a blank or zero EMI Amount — and dividing by that gives **#DIV/0!**. Go back to Chat and ask: *"Make this safe when the EMI Amount in column F is blank or zero."* You'll get something like `=IF(F3=0,"",ROUND(E3/F3,0))` or an `IFERROR` wrapper. Building that guard reflexively is what keeps a real tracker from filling with red errors.

---

## Exercise 4 — Ask Copilot Chat to Explain a Formula

### Your Turn
Copy the formula from cell **N3** (the DPD Bucket formula) in Excel and paste it into Copilot Chat with:

```
Explain this formula to me in simple terms. What does each part do, and in
what order does it evaluate?

=IF(D3>90,"Critical",IF(D3>60,"High",IF(D3>30,"Medium","Low")))
```

### What Copilot Chat Will Explain
> *"It reads the DPD in D3 from the top down. Over 90 → Critical. If not, over 60 → High. If not, over 30 → Medium. Otherwise → Low. Each IF only runs when the one before it was false, so the order matters — the highest band has to be tested first, or everything would fall into the wrong bucket."*

> **This works on any formula.** Take the ugliest formula from your own live tracker, paste it in, and ask the same question. This is the single highest-value habit from the whole session.

---

## Exercise 5 — Pivot Table: Outstanding by Product and Call Outcome

Copilot Chat **cannot build the pivot for you.** It will give you the click-path — you build it. Two minutes, and you will never need to look it up again.

### Step 1 — Ask (Copilot Chat)

```
Give me step-by-step instructions to build a PivotTable in Excel from the
range A2:L27 on this sheet, showing the total Outstanding amount for each
Product, broken down by Call Outcome. I want to see which products carry
the most escalated or unresolved balance. Tell me exactly which field goes
into which area.
```

### Step 2 — Apply (Excel)
1. Click any cell inside your data (columns A–L)
2. **Insert → PivotTable → From Table/Range** → confirm the range is **A2:L27** → **New Worksheet** → OK
3. Drag fields into the areas:
   - **Rows:** Product
   - **Columns:** Call Outcome
   - **Values:** Outstanding (₹)
4. If the value shows as **Count**, click the value field → **Value Field Settings → Sum**

### No-Pivot Alternative
If you would rather stay on the data sheet, ask Chat instead:

```
Instead of a PivotTable, give me a SUMIFS formula that totals Outstanding
for a given Product and Call Outcome, so I can build a small summary grid
with Products down the side and Call Outcomes across the top.
```

You will get something like `=SUMIFS($E$3:$E$27,$C$3:$C$27,$S3,$G$3:$G$27,T$2)` — a useful fallback when a pivot is overkill.

---

## Exercise 6 — Pivot Table: Collector Workload by DPD Bucket

This pivot uses the **DPD Bucket** column you built in Exercise 1 (column N). That column sits *after* the blank spacer column M — which changes how you select the range.

### Step 1 — Ask (Copilot Chat)

```
Give me the steps for a second PivotTable showing the count of accounts for
each Collector Name, broken down by DPD Bucket. Collector Name is column J
and DPD Bucket is column N. Note that column M between them is a blank
spacer with no header. Tell me which field goes in which area, and how to
handle that blank column.
```

### Step 2 — Apply (Excel)
1. Select **A2:Q27** (this range spans the blank spacer column M)
2. **Insert → PivotTable → From Table/Range** → **New Worksheet** → OK
3. **If Excel says *"The PivotTable field name is not valid"*** — that is the blank header in column M. Type any label into **M2** (e.g. `Spacer`), then insert the pivot again. *(The Spacer field simply goes unused.)*
4. Drag fields into the areas:
   - **Rows:** Collector Name
   - **Columns:** DPD Bucket
   - **Values:** Account ID *(defaults to Count — correct here)*

### No-Pivot Alternative
```
Instead of a PivotTable, give me a COUNTIFS formula that counts accounts for
a given Collector Name and DPD Bucket, so I can build the workload grid
manually.
```

`=COUNTIFS($J$3:$J$27,$S3,$N$3:$N$27,T$2)` — Collectors down the side, buckets across the top. This sidesteps the blank-spacer issue entirely.

---

## ⚠️ Data Handling — Read This

This is a **synthetic training dataset** — safe to describe and safe to paste. Collections data on a live tracker is not. When you carry these habits to real accounts:

- Use **Copilot Chat signed in with your BFL work account** (look for the green "Protected" / enterprise data-protection indicator)
- Never paste customer PII — names, phone numbers, account numbers, PAN — or anything under CAS / compliance restriction
- **De-identify first** — replace customer names with Cust-1, Cust-2, and paste only the columns the question actually needs

> Describing the *shape* of your data to Chat (as you did in Step 0) is almost always enough. Pasting the *whole* dataset rarely is.

---

## What Changes When You Get a Copilot Licence

Keep this session's habits — they transfer. The licence removes the copy-paste, not the thinking.

| | **Copilot Chat** *(today)* | **Copilot in Excel** *(licensed)* |
|---|---|---|
| Sees your workbook | ✗ — you describe it | ✓ — reads it directly |
| Writes formulas | ✓ | ✓ |
| **Inserts** formulas into cells | ✗ — you paste | ✓ automatic |
| Builds PivotTables | ✗ — gives you the steps | ✓ builds them |
| Analyses your data | ✓ — if you paste it in | ✓ — reads the sheet |
| Formats, charts, highlights | ✗ | ✓ |
| Explains any formula | ✓ | ✓ |

**The transferable skill:** describing your data clearly, stating the rule precisely, and checking the answer against a known number. Participants who build that habit here get more out of the licensed tool later than those who skip straight to it.

---

## Quick Reference — Collections Prompts *(this session)*

Chat writes the formula or the steps; you apply them in Excel.

| Task | Ask Copilot Chat |
|---|---|
| DPD Bucket (N) | *"Write a formula for N3: Critical if DPD (col D) > 90, High 61–90, Medium 31–60, Low 30 or less."* |
| Risk Score (O) | *"Write a formula for O3 = DPD (col D) × Outstanding (col E)."* |
| EMIs Overdue (Q) | *"Write a formula for Q3 = Outstanding (col E) ÷ EMI Amount (col F), rounded to a whole number."* |
| Explain a formula | *"Explain this formula in simple terms, part by part."* — then paste the formula |
| Pivot — outstanding by product | *"Steps to build a PivotTable from A2:L27: total Outstanding by Product × Call Outcome."* |
| Pivot — collector workload | *"Steps for a PivotTable: count by Collector Name × DPD Bucket; note the blank spacer in column M."* |
| Highlight overdue accounts | *"Give me the steps to conditionally format rows where DPD (col D) > 90 in red."* |
| Sort by risk | *"Give me the steps to sort the data by Risk Score, highest first."* |

---

## Quick Reference — Prompt Patterns *(any formula, any sheet)*

| You want | Say this |
|---|---|
| A formula | *"Write a formula for cell **X3** that…, ready to fill down to row 27"* |
| Banded categories | *"…Critical if over 90, High 61–90, Medium 31–60, Low 30 or less, based on column D."* |
| It to handle blanks / errors | *"…if the EMI Amount in column F is blank or zero, return "" instead of #DIV/0!."* |
| A simpler version | *"Rewrite this using IFS."* / *"Can this be shorter?"* |
| To understand it | *"Explain this formula in simple terms, part by part."* |
| A pivot | *"Give me step-by-step instructions to build a PivotTable that… Tell me which field goes in which area."* |
| A count / total without a pivot | *"Give me a COUNTIFS (or SUMIFS) formula for … so I can build a summary grid."* |
| Analysis on pasted data | *[paste the data]* + *"Above is my table, headers in the first row. Which…?"* |

---

*Bajaj Finance Limited | AI Academy — Collections & Recovery | Microsoft Copilot Training Programme*
